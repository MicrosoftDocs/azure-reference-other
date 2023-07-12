---
title: Supported metrics - Microsoft.DataBoxEdge/dataBoxEdgeDevices
description: Reference for Microsoft.DataBoxEdge/dataBoxEdgeDevices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DataBoxEdge/dataBoxEdgeDevices  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.DataBoxEdge/dataBoxEdgeDevices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Available Capacity<p><p>The available capacity in bytes during the reporting period. |`AvailableCapacity` |Bytes |Average |No Dimensions |Yes|
|Cloud Bytes Uploaded (Device)<p><p>The total number of bytes that is uploaded to Azure from a device during the reporting period. |`BytesUploadedToCloud` |Bytes |Average |No Dimensions |Yes|
|Cloud Bytes Uploaded (Share)<p><p>The total number of bytes that is uploaded to Azure from a share during the reporting period. |`BytesUploadedToCloudPerShare` |Bytes |Average |Share |Yes|
|Cloud Download Throughput<p><p>The cloud download throughput to Azure during the reporting period. |`CloudReadThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Cloud Download Throughput (Share)<p><p>The download throughput to Azure from a share during the reporting period. |`CloudReadThroughputPerShare` |BytesPerSecond |Average |Share |Yes|
|Cloud Upload Throughput<p><p>The cloud upload throughput  to Azure during the reporting period. |`CloudUploadThroughput` |BytesPerSecond |Average |No Dimensions |Yes|
|Cloud Upload Throughput (Share)<p><p>The upload throughput to Azure from a share during the reporting period. |`CloudUploadThroughputPerShare` |BytesPerSecond |Average |Share |Yes|
|Edge Compute - Memory Usage<p><p>Amount of RAM in Use |`HyperVMemoryUtilization` |Percent |Average |InstanceName |Yes|
|Edge Compute - Percentage CPU<p><p>Percent CPU Usage |`HyperVVirtualProcessorUtilization` |Percent |Average |InstanceName |Yes|
|Read Throughput (Network)<p><p>The read throughput of the network interface on the device in the reporting period for all volumes in the gateway. |`NICReadThroughput` |BytesPerSecond |Average |InstanceName |Yes|
|Write Throughput (Network)<p><p>The write throughput of the network interface on the device in the reporting period for all volumes in the gateway. |`NICWriteThroughput` |BytesPerSecond |Average |InstanceName |Yes|
|Total Capacity<p><p>The total capacity of the device in bytes during the reporting period. |`TotalCapacity` |Bytes |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->