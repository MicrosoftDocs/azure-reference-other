---
title: "ANOMALYDETECTION (Azure Stream Analytics) | Microsoft Docs"
description: ""
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 
ms.workload: data-services
ms.date: 02/12/2018
ms.author: sngun
---

# ANOMALYDETECTION (Azure Stream Analytics)

The ANOMALYDETECTION operator is used to detect different types of anomalies in event streams. For example, a slow decrease in free memory over a long time can be indicative of a memory leak, or the number of web service requests that are stable in a range might dramatically increase or decrease.  

The ANOMALYDETECTION operator detects three types of anomalies: 

* **Bi-directional Level Change**: A sustained increase or decrease in the level of values, both upward and downward. This value is different from spikes and dips, which are instantaneous or short-lived changes.  

* **Slow Positive Trend**: A slow increase in the trend over time.  

* **Slow Negative Trend**: A slow decrease in the trend over time.  

When using the ANOMALYDETECTION operator, you must specify the **Limit Duration** clause. This clause specifies the time interval (how far back in history from the current event) should be considered when detecting anomalies. This operator can optionally be limited to only events that match a certain property or condition by using the **When** clause. This operator can also optionally process groups of events separately based on the key specified in the **Partition by** clause. Training and prediction occur independently for each partition. To learn about training models and scoring events by using ANOMALYDETECTION operator, refer to the [anomaly detection algorithm](https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-machine-learning-anomaly-detection) article. 

## Syntax for ANOMALYDETECTION operator

`ANOMALYDETECTION(<scalar_expression>) OVER ([PARTITION BY <partition key>] LIMIT DURATION(<unit>, <length>) [WHEN boolean_expression])` 

### Arguments

* **scalar_expression** - The scalar expression over which the anomaly detection is performed. Allowed values for this parameter include Float or Bigint data types that return a single (scalar) value. The wildcard expression **\*** is not allowed. Scalar expression cannot contain other analytic functions or external functions. 

* **partition_by_clause** - The `PARTITION BY <partition key>` clause divides the
learning and training across separate partitions. In other words, a separate
model would be used per value of `<partition key>` and only events with that
value would be used for learning and training in that model. For example, the following query trains and scores a reading against other readings of the same sensor only:

  `SELECT sensorId, reading, ANOMALYDETECTION(reading) OVER(PARTITION BY sensorId LIMIT DURATION(hour, 1)) FROM input`

* **limit_duration clause** `DURATION(<unit>, <length>)` - Specifies the time interval (how far back in history from the current event) should be considered when detecting anomalies. See [DATEDIFF](https://msdn.microsoft.com/azure/stream-analytics/reference/datediff-azure-stream-analytics) for a detailed description of supported units and their abbreviations. 

* **when_clause** - Specifies a boolean condition for the events considered in the
anomaly detection computation.

### Return types

The ANOMALYDETECTION operator returns a record containing all three scores as its output. The
properties associated with the different types of anomaly detectors are:

- BiLevelChangeScore
- SlowPosTrendScore
- SlowNegTrendScore

To extract the individual values out of the record, use the **GetRecordPropertyValue** function. For example:

`SELECT id, val FROM input WHERE (GetRecordPropertyValue(ANOMALYDETECTION(val) OVER(LIMIT DURATION(hour, 1)), 'BiLevelChangeScore')) > 3.25` 

Anomaly of a type is detected when one of the anomaly scores crosses a threshold. The threshold can be any floating-point number >= 0. The threshold is a tradeoff between sensitivity and confidence. For example, a lower threshold would make detection more sensitive to changes and generate more alerts, whereas a higher threshold could make detection less sensitive and more confident but mask some anomalies. The exact threshold value to use depends on the scenario. There is no upper limit, but the recommended range is 3.25-5. 

**Examples**  

`SELECT id, val, ANOMALYDETECTION(val) OVER(PARTITION BY id LIMIT DURATION(hour, 1) WHEN id > 100) FROM input`

## Next Steps  
 [ISFIRST &#40;Azure Stream Analytics&#41;](isfirst-azure-stream-analytics.md)   
 [LAG &#40;Azure Stream Analytics&#41;](lag-azure-stream-analytics.md)  
