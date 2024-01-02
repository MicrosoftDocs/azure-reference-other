---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StreamAnalytics/streamingjobs, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Failed Function Requests**<p><p>Failed Function Requests |`AMLCalloutFailedRequests` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Function Events**<p><p>Function Events |`AMLCalloutInputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Function Requests**<p><p>Function Requests |`AMLCalloutRequests` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Data Conversion Errors**<p><p>Data Conversion Errors |`ConversionErrors` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Deserialization Errors**<p><p>Input Deserialization Errors |`DeserializationError` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Out of order Events**<p><p>Out of order Events |`DroppedOrAdjustedEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Early Input Events**<p><p>Early Input Events |`EarlyInputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Runtime Errors**<p><p>Runtime Errors |`Errors` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Event Bytes**<p><p>Input Event Bytes |`InputEventBytes` |Bytes |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Events**<p><p>Input Events |`InputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Backlogged Input Events**<p><p>Backlogged Input Events |`InputEventsSourcesBacklogged` |Count |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Sources Received**<p><p>Input Sources Received |`InputEventsSourcesPerSecond` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Late Input Events**<p><p>Late Input Events |`LateInputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Output Events**<p><p>Output Events |`OutputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Watermark Delay**<p><p>Watermark Delay |`OutputWatermarkDelaySeconds` |Seconds |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**CPU % Utilization**<p><p>CPU % Utilization |`ProcessCPUUsagePercentage` |Percent |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**SU (Memory) % Utilization**<p><p>SU (Memory) % Utilization |`ResourceUtilization` |Percent |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|