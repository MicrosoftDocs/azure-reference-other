---
title: Supported metrics - Microsoft.NetworkCloud/storageAppliances
description: Reference for Microsoft.NetworkCloud/storageAppliances metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.NetworkCloud/storageAppliances  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.NetworkCloud/storageAppliances resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Nexus Storage Alerts Total<p><p>Number of alert events |`PurefaAlertsTotal` |Count |Average |Severity |No|
|Nexus Storage Array Avg Block Bytes<p><p>Average block size |`PurefaArrayPerformanceAvgBlockBytes` |Bytes |Average |Dimension |No|
|Nexus Storage Array Bandwidth Bytes<p><p>Array throughput in bytes per second |`PurefaArrayPerformanceBandwidthBytes` |Bytes |Average |Dimension |No|
|Nexus Storage Array IOPS<p><p>Storage array IOPS |`PurefaArrayPerformanceIOPS` |Count |Average |Dimension |No|
|Nexus Storage Array Latency (Microseconds)<p><p>Storage array latency in microseconds |`PurefaArrayPerformanceLatencyUsec` |MilliSeconds |Average |Dimension |No|
|Nexus Storage Array Queue Depth<p><p>Storage array queue depth |`PurefaArrayPerformanceQdepth` |Bytes |Average |No Dimensions |No|
|Nexus Storage Array Capacity Bytes<p><p>Storage array overall space capacity |`PurefaArraySpaceCapacityBytes` |Bytes |Average |No Dimensions |No|
|Nexus Storage Array Space Datareduction Ratio<p><p>Storage array overall data reduction |`PurefaArraySpaceDatareductionRatio` |Percent |Average |No Dimensions |No|
|Nexus Storage Array Space Provisioned Bytes<p><p>Storage array overall provisioned space |`PurefaArraySpaceProvisionedBytes` |Bytes |Average |No Dimensions |No|
|Nexus Storage Array Space Used Bytes<p><p>Storage Array overall used space |`PurefaArraySpaceUsedBytes` |Bytes |Average |Dimension |No|
|Nexus Storage Hardware Component Health<p><p>Storage array hardware component health status |`PurefaHardwareComponentHealth` |Count |Average |Component, Controller, Index |No|
|Nexus Storage Hardware Power Volts<p><p>Storage array hardware power supply voltage |`PurefaHardwarePowerVolts` |Unspecified |Average |Power Supply |No|
|Nexus Storage Hardware Temperature Celsius<p><p>Storage array hardware temperature sensors |`PurefaHardwareTemperatureCelsius` |Unspecified |Average |Controller, Sensor |No|
|Nexus Storage Host Bandwidth Bytes<p><p>Storage array host bandwidth in bytes per second |`PurefaHostPerformanceBandwidthBytes` |Bytes |Average |Dimension, Host |No|
|Nexus Storage Host IOPS<p><p>Storage array host IOPS |`PurefaHostPerformanceIOPS` |Count |Average |Dimension, Host |No|
|Nexus Storage Host Latency (Microseconds)<p><p>Storage array host latency in microseconds |`PurefaHostPerformanceLatencyUsec` |MilliSeconds |Average |Dimension, Host |No|
|Nexus Storage Host Space Bytes<p><p>Storage array host space in bytes |`PurefaHostSpaceBytes` |Bytes |Average |Dimension, Host |No|
|Nexus Storage Host Space Datareduction Ratio<p><p>Storage array host volumes data reduction ratio |`PurefaHostSpaceDatareductionRatio` |Percent |Average |Host |No|
|Nexus Storage Host Space Size Bytes<p><p>Storage array host volumes size |`PurefaHostSpaceSizeBytes` |Bytes |Average |Host |No|
|Nexus Storage Info (Preview)<p><p>Storage array system information |`PurefaInfo` |Unspecified |Average |Array Name |No|
|Nexus Storage Volume Performance IOPS<p><p>Storage array volume IOPS |`PurefaVolumePerformanceIOPS` |Count |Average |Dimension, Volume |No|
|Nexus Storage Volume Performance Latency (Microseconds)<p><p>Storage array volume latency in microseconds |`PurefaVolumePerformanceLatencyUsec` |MilliSeconds |Average |Dimension, Volume |No|
|Nexus Storage Volume Performance Throughput Bytes<p><p>Storage array volume throughput |`PurefaVolumePerformanceThroughputBytes` |Bytes |Average |Dimension, Volume |No|
|Nexus Storage Volume Space Bytes<p><p>Storage array volume space in bytes |`PurefaVolumeSpaceBytes` |Bytes |Average |Dimension, Volume |No|
|Nexus Storage Volume Space Datareduction Ratio<p><p>Storage array overall data reduction |`PurefaVolumeSpaceDatareductionRatio` |Percent |Average |Volume |No|
|Nexus Storage Volume Space Size Bytes<p><p>Storage array volumes size |`PurefaVolumeSpaceSizeBytes` |Bytes |Average |Volume |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->