---
title: "Reference Data JOIN"
description: "Used to correlate persisted historical data or a slow changing dataset (aka. reference data) with the real-time event stream to make smarter decisions about the system."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# Reference Data JOIN
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

In a usual scenario, we use an event processing engine to compute streaming data with very low latency. In many cases users need to correlate persisted historical data or a slow changing dataset (aka. reference data) with the real-time event stream to make smarter decisions about the system. For example, join my event stream to a static dataset which maps IP Addresses to locations. This is the only JOIN supported in Stream Analytics where a temporal bound is not necessary. Reference data can also be used to have device-specific threshold values.
  
## Example  
 If a commercial vehicle is registered with the Toll Company, they can pass through the toll booth without being stopped for inspection. We will use a commercial vehicle registration lookup table to identify all commercial vehicles with expired registration.  
  
```SQL  
SELECT I1.EntryTime, I1.LicensePlate, I1.TollId, R.RegistrationId  
FROM Input1 I1 TIMESTAMP BY EntryTime  
JOIN Registration R  
ON I1.LicensePlate = R.LicensePlate  
WHERE R.Expired = '1'
```  
  
## Particularities of Reference Data JOIN

- Using Reference Data JOIN requires that an input source for Reference Data is defined.  
- Reference data JOIN is supported for inner JOIN (default) and left outer JOIN, with reference data on the right side of the JOIN operator.
- Data types are an important aspect in the evaluation of the join predicate (`ON` clause). Similar values on different data types (`1.0` and `"1"`) may not be matched. [Explicitely converting](data-types-azure-stream-analytics.md) keys to a common type is recommended.
- Reference data can be static (loaded only once) or dynamic (refreshed regularly). However even in the dynamic case, reference data does not make the time progress so the stream on the left side needs to get new events in order to produce outputs. See also [how time progresses in azure stream analytics](/azure/stream-analytics/stream-analytics-time-handling#how-time-progresses-in-azure-stream-analytics) for more information.

## Performance considerations

To prevent performance degradations, reference join predicates (`ON` clause) should be defined via simple key equalities (`ON s.myKey = r.myKey`). Using complex expressions, or inequalities, will internally result in cross joins followed by filters (full scan vs lookup), which can severly impact the overall latency.

When possible, move these complex expressions to the `WHERE` clause of the query step, or join the same Reference Data multiple times each with simpler conditions.

 ## See Also  
- [JOIN](join-azure-stream-analytics.md)
- [Reference data input](/azure/stream-analytics/stream-analytics-use-reference-data)
-  [Use reference data from a SQL Database for an Azure Stream Analytics job](/azure/stream-analytics/sql-reference-data)
- [Process configurable threshold-based rules in Azure Stream Analytics](/azure/stream-analytics/stream-analytics-threshold-based-rules)
 
