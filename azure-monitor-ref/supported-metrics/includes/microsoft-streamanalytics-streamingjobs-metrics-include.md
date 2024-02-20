---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.StreamAnalytics/streamingjobs, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|**Failed Function Requests**<br><br>Failed Function Requests |`AMLCalloutFailedRequests` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Function Events**<br><br>Function Events |`AMLCalloutInputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Function Requests**<br><br>Function Requests |`AMLCalloutRequests` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Data Conversion Errors**<br><br>Data Conversion Errors |`ConversionErrors` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Deserialization Errors**<br><br>Input Deserialization Errors |`DeserializationError` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Out of order Events**<br><br>Out of order Events |`DroppedOrAdjustedEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Early Input Events**<br><br>Early Input Events |`EarlyInputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Runtime Errors**<br><br>Runtime Errors |`Errors` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Event Bytes**<br><br>Input Event Bytes |`InputEventBytes` |Bytes |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Events**<br><br>Input Events |`InputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Backlogged Input Events**<br><br>Backlogged Input Events |`InputEventsSourcesBacklogged` |Count |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Input Sources Received**<br><br>Input Sources Received |`InputEventsSourcesPerSecond` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Late Input Events**<br><br>Late Input Events |`LateInputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Output Events**<br><br>Output Events |`OutputEvents` |Count |Total |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**Watermark Delay**<br><br>Watermark Delay |`OutputWatermarkDelaySeconds` |Seconds |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**CPU % Utilization**<br><br>CPU % Utilization |`ProcessCPUUsagePercentage` |Percent |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|
|**SU (Memory) % Utilization**<br><br>SU (Memory) % Utilization |`ResourceUtilization` |Percent |Average, Maximum, Minimum |`LogicalName`, `PartitionId`, `ProcessorInstance`, `NodeName`|PT1M |Yes|