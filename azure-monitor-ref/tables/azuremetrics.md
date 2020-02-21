---
title: Azure Monitor Logs reference - AzureMetrics
description: Reference for AzureMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# AzureMetrics

 Metric data emitted by Azure services that measure their health and performance.

## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string|OpsManagerfor all records in this table.|
|TimeGenerated|datetime|Date and time the record was created.|
|ResourceId|string|Resource ID of the Azure resource reporting the metric. Same as _ResourceId present for backward compatibility reasons. _ResourceId should be used|
|OperationName|string|Deprecated|
|OperationVersion|string|Deprecated|
|Category|string|Deprecated|
|ResultType|string|Reduces the set of data collected. The syntax allowed depends on the operation. See the operation's description for details.|
|ResultSignature|string|Deprecated|
|ResultDescription|string|Deprecated|
|DurationMs|long|Deprecated|
|CallerIpAddress|string|Deprecated|
|CorrelationId|string|Deprecated|
|Resource|string|Resource name of the Azure resource reporting the metric.|
|ResourceGroup|string|Resource group name of the Azure resource reporting the metric.|
|ResourceProvider|string|Resource provider of the Azure resource reporting the metric.|
|SubscriptionId|string|Subscription id of the Azure resource reporting the metric.|
|MetricName|string|Display name of the metric.|
|Total|real|Sum of all of the values in the time range.|
|Count|real|Number of samples collected during the time range. Can be used to determine the number of values that contributed to the average value.|
|Maximum|real|Maximum value collected during in the time range.|
|Minimum|real|Minimum value collected during in the time range.|
|Average|real||
|TimeGrain|string|Time grain of the metric e.g. PT1M|
|UnitName|string|Unit of the metric. Examples include Seconds Percent Bytes.|
|RemoteIPCountry|string|Deprecated|
|RemoteIPLatitude|real|Deprecated|
|RemoteIPLongitude|real|Deprecated|
|MaliciousIP|string|Deprecated|
|IndicatorThreatType|string|Deprecated|
|Description|string|Deprecated|
|TLPLevel|string|Deprecated|
|Confidence|string|Deprecated|
|Severity|int|Deprecated|
|FirstReportedDateTime|string|Deprecated|
|LastReportedDateTime|string|Deprecated|
|IsActive|string|Deprecated|
|Type|string||
|_ResourceId|string||
