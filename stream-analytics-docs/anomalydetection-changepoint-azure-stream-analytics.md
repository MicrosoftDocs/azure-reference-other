---
title: "AnomalyDetection_ChangePoint (Azure Stream Analytics) | Microsoft Docs"
description: ""
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
ms.service: stream-analytics
ms.topic: reference
ms.assetid: 
ms.workload: data-services
ms.date: 02/12/2018
ms.author: mamccrea
---

# AnomalyDetection_ChangePoint (Azure Stream Analytics) (Preview)

Persistent anomalies in a time series event stream are changes in the distribution of values in the event stream, such as level changes and trends. In Stream Analytics, anomalies are detected using the Machine Learning based **AnomalyDetection_ChangePoint** operator. The underlying Machine Learning model uses the Exchangeability Martingales algorithm.

These changes are persistent and last much longer than spikes and dips, possibly indicating a catastrophic event.

## Syntax

```SQL
AnomalyDetection_ChangePoint(
		<scalar_expression>, 
		<confidence>, 
		<historySize>)
	OVER ([PARTITION BY <partition key>] 
		LIMIT DURATION(<unit>, <length>)
	[WHEN boolean_expression])

```

## Arguments

**scalar_expression**

The event column or computed field over which the model performs anomaly detection. Allowed values for this parameter include FLOAT or BIGINT data types that return a single (scalar) value.

The wildcard expression * is not allowed. Also, *scalar_expression* cannot contain other analytic functions or external functions.

**confidence**

A percentage number from 1.00 to 100 (inclusive) that sets the sensitivity of the Machine Learning model. The lower the confidence, the higher the number of anomalies detected, and vice versa. You are advised to start from an arbitrary number between 70 and 90 and adjust this based on the results observed in development or testing.

**historySize**

The number of events in a sliding window that the model continuously learns from and uses for scoring the next event for anomalousness. Typically, this should represent the period of time of normal behavior to enable the model to flag a subsequent anomaly. 
Operationally, users are advised to start with an educated guess using historical logs, and adjust it based on the results observed in dev/test.

**OVER ([ partition_by_clause ] limit_duration_clause [when_clause])**

**partition_by_clause**

Users may want to partition a model's training based on a particular column in the events. For example, if several sensors with different sensor IDs are feeding into the same Stream Analytics job, partitioning by sensor ID trains a different Machine Learning model for each sensor as every sensor’s behavior patterns may be slightly different. 

The model applies the same function parameter settings across all the partitions.

**limit_duration_clause** DURATION(<unit>, <length>)

This is the size of the sliding window within Stream Analytics in terms of time. We recommend setting the size of this time window to be equal to the time it takes to generate *historySize* number of events in steady state. The maximum supported value is 7 days (as with all other Stream Analytics windows and durations). For persistent anomalies, it is recommended to set the window size longer than anomaly duration based on historical observations to avoid false positives. 

**when_clause**

Specifies boolean condition for the events to be provided to the model to perform anomaly detection. The *when_clause* is optional.

## Return Types

The function returns a nested record composed of the following columns:

**IsAnomaly**

A BIGINT (0 or 1) indicating if the event was anomalous or not.

**Score**

The computed Martingale score (float) indicating how anomalous an event is. This score grows exponentially with anomalous values.

## Examples

The following example assumes an event every 5 minutes and example 2 assumes an event every second. Confidence level is set at 75 for both models. 

```SQL
AnomalyDetection_ChangePoint(reading, 75, 72)
	OVER (LIMIT DURATION(hour, 6))

AnomalyDetection_ChangePoint(temperature, 75, 120)
	OVER ([PARTITION BY sensorId] LIMIT DURATION(second, 120))
```

Basic example, assuming a uniform input rate of 1 event per second in a 20 minute sliding window with a history size of 1200 events. The final SELECT statement extracts and outputs the score and anomaly status with a confidence level of 80%.

```SQL
WITH AnomalyDetectionStep AS
(
SELECT
EVENTENQUEUEDUTCTIME as time,
CAST(temperature as float) as temp,
AnomalyDetection_ChangePoint(CAST(temperature as float), 80, 1200) 
OVER(LIMIT DURATION(minute, 20)) as ChangePointScores
FROM input
)

SELECT
time,
temp,
CAST(GetRecordPropertyValue(ChangePointScores, 'Score') as float) as
ChangePointScore,
CAST(GetRecordPropertyValue(ChangePointScores, 'IsAnomaly') as bigint) as
IsChangePointAnomaly

INTO output
FROM AnomalyDetectionStep
```

Example with a non-uniform input stream that is made uniform using a tumbling window of 1 second:

```SQL
WITH SmootheningStep AS
(
SELECT
System.Timestamp as time,
AVG(CAST(temperature as float)) as temp
FROM input
GROUP BY TUMBLINGWINDOW(second, 1)
),
AnomalyDetectionStep AS
(
SELECT
time,
temp,
AnomalyDetection_ChangePoint(temp, 80, 1200) 
OVER(LIMIT DURATION(minute, 20)) as ChangePointScores
FROM SmootheningStep
)

SELECT
time,
temp,
CAST(GetRecordPropertyValue(ChangePointScores, 'Score') as float) as
ChangePointScore,
CAST(GetRecordPropertyValue(ChangePointScores, 'IsAnomaly') as bigint) as
IsChangePointAnomaly

INTO output
FROM AnomalyDetectionStep
```

Example with a partitioned query to train a separate model per sensor:

```SQL
WITH AnomalyDetectionStep AS
(
SELECT
sensorid,
System.Timestamp as time,
CAST(temperature as float) as temp,
AnomalyDetection_ChangePoint(CAST(temperature as float), 80, 1200) 
OVER(PARTITION BY sensorid
LIMIT DURATION(minute, 20)) as ChangePointScores
FROM input
)

SELECT
CAST (sensorid as nvarchar(max)) as sensoridstring,
time,
temp,
CAST(GetRecordPropertyValue(ChangePointScores, 'Score') as float) as
ChangePointScore,
CAST(GetRecordPropertyValue(ChangePointScores, 'IsAnomaly') as bigint) as
IsChangePointAnomaly

INTO output
FROM AnomalyDetectionStep
```
