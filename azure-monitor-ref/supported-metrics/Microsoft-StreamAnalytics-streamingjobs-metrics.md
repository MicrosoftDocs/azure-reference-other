---
title: Supported metrics - Microsoft.StreamAnalytics/streamingjobs
description: Reference for Microsoft.StreamAnalytics/streamingjobs metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.StreamAnalytics/streamingjobs  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.StreamAnalytics/streamingjobs resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Failed Function Requests<p><p>Failed Function Requests |`AMLCalloutFailedRequests` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Function Events<p><p>Function Events |`AMLCalloutInputEvents` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Function Requests<p><p>Function Requests |`AMLCalloutRequests` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Data Conversion Errors<p><p>Data Conversion Errors |`ConversionErrors` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Input Deserialization Errors<p><p>Input Deserialization Errors |`DeserializationError` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Out of order Events<p><p>Out of order Events |`DroppedOrAdjustedEvents` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Early Input Events<p><p>Early Input Events |`EarlyInputEvents` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Runtime Errors<p><p>Runtime Errors |`Errors` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Input Event Bytes<p><p>Input Event Bytes |`InputEventBytes` |Bytes |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Input Events<p><p>Input Events |`InputEvents` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Backlogged Input Events<p><p>Backlogged Input Events |`InputEventsSourcesBacklogged` |Count |Maximum |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Input Sources Received<p><p>Input Sources Received |`InputEventsSourcesPerSecond` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Late Input Events<p><p>Late Input Events |`LateInputEvents` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Output Events<p><p>Output Events |`OutputEvents` |Count |Total |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|Watermark Delay<p><p>Watermark Delay |`OutputWatermarkDelaySeconds` |Seconds |Maximum |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|CPU % Utilization<p><p>CPU % Utilization |`ProcessCPUUsagePercentage` |Percent |Maximum |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|
|SU (Memory) % Utilization<p><p>SU (Memory) % Utilization |`ResourceUtilization` |Percent |Maximum |LogicalName, PartitionId, ProcessorInstance, NodeName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->