---
title: Supported metrics - Microsoft.Compute/virtualMachineScaleSets/virtualMachines
description: Reference for Microsoft.Compute/virtualMachineScaleSets/virtualMachines metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Compute/virtualMachineScaleSets/virtualMachines  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Compute/virtualMachineScaleSets/virtualMachines resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Available Memory Bytes (Preview)<p><p>Amount of physical memory, in bytes, immediately available for allocation to a process or for system use in the Virtual Machine |`Available Memory Bytes` |Bytes |Average |No Dimensions |Yes|
|CPU Credits Consumed<p><p>Total number of credits consumed by the Virtual Machine. Only available on B-series burstable VMs |`CPU Credits Consumed` |Count |Average |No Dimensions |Yes|
|CPU Credits Remaining<p><p>Total number of credits available to burst. Only available on B-series burstable VMs |`CPU Credits Remaining` |Count |Average |No Dimensions |Yes|
|Data Disk Bandwidth Consumed Percentage<p><p>Percentage of data disk bandwidth consumed per minute |`Data Disk Bandwidth Consumed Percentage` |Percent |Average |LUN |Yes|
|Data Disk IOPS Consumed Percentage<p><p>Percentage of data disk I/Os consumed per minute |`Data Disk IOPS Consumed Percentage` |Percent |Average |LUN |Yes|
|Data Disk Max Burst Bandwidth<p><p>Maximum bytes per second throughput Data Disk can achieve with bursting |`Data Disk Max Burst Bandwidth` |Count |Average |LUN |Yes|
|Data Disk Max Burst IOPS<p><p>Maximum IOPS Data Disk can achieve with bursting |`Data Disk Max Burst IOPS` |Count |Average |LUN |Yes|
|Data Disk Queue Depth<p><p>Data Disk Queue Depth(or Queue Length) |`Data Disk Queue Depth` |Count |Average |LUN |Yes|
|Data Disk Read Bytes/Sec<p><p>Bytes/Sec read from a single disk during monitoring period |`Data Disk Read Bytes/sec` |BytesPerSecond |Average |LUN |Yes|
|Data Disk Read Operations/Sec<p><p>Read IOPS from a single disk during monitoring period |`Data Disk Read Operations/Sec` |CountPerSecond |Average |LUN |Yes|
|Data Disk Target Bandwidth<p><p>Baseline bytes per second throughput Data Disk can achieve without bursting |`Data Disk Target Bandwidth` |Count |Average |LUN |Yes|
|Data Disk Target IOPS<p><p>Baseline IOPS Data Disk can achieve without bursting |`Data Disk Target IOPS` |Count |Average |LUN |Yes|
|Data Disk Used Burst BPS Credits Percentage<p><p>Percentage of Data Disk burst bandwidth credits used so far |`Data Disk Used Burst BPS Credits Percentage` |Percent |Average |LUN |Yes|
|Data Disk Used Burst IO Credits Percentage<p><p>Percentage of Data Disk burst I/O credits used so far |`Data Disk Used Burst IO Credits Percentage` |Percent |Average |LUN |Yes|
|Data Disk Write Bytes/Sec<p><p>Bytes/Sec written to a single disk during monitoring period |`Data Disk Write Bytes/sec` |BytesPerSecond |Average |LUN |Yes|
|Data Disk Write Operations/Sec<p><p>Write IOPS from a single disk during monitoring period |`Data Disk Write Operations/Sec` |CountPerSecond |Average |LUN |Yes|
|Disk Read Bytes<p><p>Bytes read from disk during monitoring period |`Disk Read Bytes` |Bytes |Total |No Dimensions |Yes|
|Disk Read Operations/Sec<p><p>Disk Read IOPS |`Disk Read Operations/Sec` |CountPerSecond |Average |No Dimensions |Yes|
|Disk Write Bytes<p><p>Bytes written to disk during monitoring period |`Disk Write Bytes` |Bytes |Total |No Dimensions |Yes|
|Disk Write Operations/Sec<p><p>Disk Write IOPS |`Disk Write Operations/Sec` |CountPerSecond |Average |No Dimensions |Yes|
|Inbound Flows<p><p>Inbound Flows are number of current flows in the inbound direction (traffic going into the VM) |`Inbound Flows` |Count |Average |No Dimensions |Yes|
|Inbound Flows Maximum Creation Rate<p><p>The maximum creation rate of inbound flows (traffic going into the VM) |`Inbound Flows Maximum Creation Rate` |CountPerSecond |Average |No Dimensions |Yes|
|Network In Billable (Deprecated)<p><p>The number of billable bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic) (Deprecated) |`Network In` |Bytes |Total |No Dimensions |Yes|
|Network In Total<p><p>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic) |`Network In Total` |Bytes |Total |No Dimensions |Yes|
|Network Out Billable (Deprecated)<p><p>The number of billable bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic) (Deprecated) |`Network Out` |Bytes |Total |No Dimensions |Yes|
|Network Out Total<p><p>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic) |`Network Out Total` |Bytes |Total |No Dimensions |Yes|
|OS Disk Bandwidth Consumed Percentage<p><p>Percentage of operating system disk bandwidth consumed per minute |`OS Disk Bandwidth Consumed Percentage` |Percent |Average |LUN |Yes|
|OS Disk IOPS Consumed Percentage<p><p>Percentage of operating system disk I/Os consumed per minute |`OS Disk IOPS Consumed Percentage` |Percent |Average |LUN |Yes|
|OS Disk Max Burst Bandwidth<p><p>Maximum bytes per second throughput OS Disk can achieve with bursting |`OS Disk Max Burst Bandwidth` |Count |Average |LUN |Yes|
|OS Disk Max Burst IOPS<p><p>Maximum IOPS OS Disk can achieve with bursting |`OS Disk Max Burst IOPS` |Count |Average |LUN |Yes|
|OS Disk Queue Depth<p><p>OS Disk Queue Depth(or Queue Length) |`OS Disk Queue Depth` |Count |Average |No Dimensions |Yes|
|OS Disk Read Bytes/Sec<p><p>Bytes/Sec read from a single disk during monitoring period for OS disk |`OS Disk Read Bytes/sec` |BytesPerSecond |Average |No Dimensions |Yes|
|OS Disk Read Operations/Sec<p><p>Read IOPS from a single disk during monitoring period for OS disk |`OS Disk Read Operations/Sec` |CountPerSecond |Average |No Dimensions |Yes|
|OS Disk Target Bandwidth<p><p>Baseline bytes per second throughput OS Disk can achieve without bursting |`OS Disk Target Bandwidth` |Count |Average |LUN |Yes|
|OS Disk Target IOPS<p><p>Baseline IOPS OS Disk can achieve without bursting |`OS Disk Target IOPS` |Count |Average |LUN |Yes|
|OS Disk Used Burst BPS Credits Percentage<p><p>Percentage of OS Disk burst bandwidth credits used so far |`OS Disk Used Burst BPS Credits Percentage` |Percent |Average |LUN |Yes|
|OS Disk Used Burst IO Credits Percentage<p><p>Percentage of OS Disk burst I/O credits used so far |`OS Disk Used Burst IO Credits Percentage` |Percent |Average |LUN |Yes|
|OS Disk Write Bytes/Sec<p><p>Bytes/Sec written to a single disk during monitoring period for OS disk |`OS Disk Write Bytes/sec` |BytesPerSecond |Average |No Dimensions |Yes|
|OS Disk Write Operations/Sec<p><p>Write IOPS from a single disk during monitoring period for OS disk |`OS Disk Write Operations/Sec` |CountPerSecond |Average |No Dimensions |Yes|
|Outbound Flows<p><p>Outbound Flows are number of current flows in the outbound direction (traffic going out of the VM) |`Outbound Flows` |Count |Average |No Dimensions |Yes|
|Outbound Flows Maximum Creation Rate<p><p>The maximum creation rate of outbound flows (traffic going out of the VM) |`Outbound Flows Maximum Creation Rate` |CountPerSecond |Average |No Dimensions |Yes|
|Percentage CPU<p><p>The percentage of allocated compute units that are currently in use by the Virtual Machine(s) |`Percentage CPU` |Percent |Average |No Dimensions |Yes|
|Premium Data Disk Cache Read Hit<p><p>Premium Data Disk Cache Read Hit |`Premium Data Disk Cache Read Hit` |Percent |Average |LUN |Yes|
|Premium Data Disk Cache Read Miss<p><p>Premium Data Disk Cache Read Miss |`Premium Data Disk Cache Read Miss` |Percent |Average |LUN |Yes|
|Premium OS Disk Cache Read Hit<p><p>Premium OS Disk Cache Read Hit |`Premium OS Disk Cache Read Hit` |Percent |Average |No Dimensions |Yes|
|Premium OS Disk Cache Read Miss<p><p>Premium OS Disk Cache Read Miss |`Premium OS Disk Cache Read Miss` |Percent |Average |No Dimensions |Yes|
|VM Cached Bandwidth Consumed Percentage<p><p>Percentage of cached disk bandwidth consumed by the VM |`VM Cached Bandwidth Consumed Percentage` |Percent |Average |No Dimensions |Yes|
|VM Cached IOPS Consumed Percentage<p><p>Percentage of cached disk IOPS consumed by the VM |`VM Cached IOPS Consumed Percentage` |Percent |Average |No Dimensions |Yes|
|VM Uncached Bandwidth Consumed Percentage<p><p>Percentage of uncached disk bandwidth consumed by the VM |`VM Uncached Bandwidth Consumed Percentage` |Percent |Average |No Dimensions |Yes|
|VM Uncached IOPS Consumed Percentage<p><p>Percentage of uncached disk IOPS consumed by the VM |`VM Uncached IOPS Consumed Percentage` |Percent |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->