---
title: "AnomalyDetection_ChangePoint"
description: "Describes the AnomalyDetection_ChangePoint function supported by the Stream Analytics Query Language."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# AnomalyDetection_ChangePoint

Detects persistent anomalies in a time series event stream. The underlying machine learning model uses the Exchangeability Martingales algorithm.

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

A percentage number from 1.00 to 100 (inclusive) that sets the sensitivity of the machine learning model. The lower the confidence, the higher the number of anomalies detected, and vice versa. Start from an arbitrary number between 70 and 90 and adjust this based on the results observed in development or testing.

**historySize**

The number of events in a sliding window that the model continuously learns from and uses for scoring the next event for anomalousness. Typically, this should represent the period of time of normal behavior to enable the model to flag a subsequent anomaly. Start with an educated guess using historical logs, and adjust based on the results observed in development or test.

**OVER ([ partition_by_clause ] limit_duration_clause [when_clause])**

**partition_by_clause**

Used to partition a model's training based on a particular column in the events. The model applies the same function parameter settings across all the partitions.

**limit_duration_clause** DURATION(unit, length)

The size of the sliding window within Stream Analytics in terms of time. The recommended size of this time window is the equivalent of the time it takes to generate *historySize* number of events in steady state.

**when_clause**

Specifies boolean condition for the events to be provided to the model to perform anomaly detection. The *when_clause* is optional.

## Return Types

The function returns a nested record composed of the following columns:

**IsAnomaly**

A BIGINT (0 or 1) indicating if the event was anomalous or not.

**Score**

The computed Martingale score (float) indicating how anomalous an event is. This score grows exponentially with anomalous values.

## Examples

In the following query sample, the first query assumes an event every 5 minutes, and the second query assumes an event every second. The confidence level is set at 75 for both models.

```SQL
AnomalyDetection_ChangePoint(reading, 75, 72)
    OVER (LIMIT DURATION(hour, 6))

AnomalyDetection_ChangePoint(temperature, 75, 120)
    OVER ([PARTITION BY sensorId] LIMIT DURATION(second, 120))
```

Example assuming a uniform input rate of 1 event per second in a 20 minute sliding window with a history size of 1200 events. The final SELECT statement extracts and outputs the score and anomaly status with a confidence level of 80%.

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
System.Timestamp() as time,
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
System.Timestamp() as time,
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
