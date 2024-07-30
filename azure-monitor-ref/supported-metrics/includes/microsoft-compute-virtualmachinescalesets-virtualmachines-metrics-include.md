---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Compute/virtualMachineScaleSets/virtualMachines, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Available Memory Bytes (Preview)**<br><br>Amount of physical memory, in bytes, immediately available for allocation to a process or for system use in the Virtual Machine |`Available Memory Bytes` |Bytes |Average |\<none\>|PT1M |Yes|
|**CPU Credits Consumed**<br><br>Total number of credits consumed by the Virtual Machine. Only available on B-series burstable VMs |`CPU Credits Consumed` |Count |Average |\<none\>|PT1M |Yes|
|**CPU Credits Remaining**<br><br>Total number of credits available to burst. Only available on B-series burstable VMs |`CPU Credits Remaining` |Count |Average |\<none\>|PT1M |Yes|
|**Data Disk Bandwidth Consumed Percentage**<br><br>Percentage of data disk bandwidth consumed per minute. Only available on VM series that support premium storage. |`Data Disk Bandwidth Consumed Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**Data Disk IOPS Consumed Percentage**<br><br>Percentage of data disk I/Os consumed per minute. Only available on VM series that support premium storage. |`Data Disk IOPS Consumed Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**Data Disk Latency (Preview)**<br><br>Average time to complete each IO during monitoring period for Data Disk. Values are in milliseconds. |`Data Disk Latency` |Milliseconds |Average |`LUN`|PT1M |Yes|
|**Data Disk Max Burst Bandwidth**<br><br>Maximum bytes per second throughput Data Disk can achieve with bursting |`Data Disk Max Burst Bandwidth` |Count |Average |`LUN`|PT1M |Yes|
|**Data Disk Max Burst IOPS**<br><br>Maximum IOPS Data Disk can achieve with bursting |`Data Disk Max Burst IOPS` |Count |Average |`LUN`|PT1M |Yes|
|**Data Disk Queue Depth**<br><br>Data Disk Queue Depth(or Queue Length) |`Data Disk Queue Depth` |Count |Average |`LUN`|PT1M |Yes|
|**Data Disk Read Bytes/Sec**<br><br>Bytes/Sec read from a single disk during monitoring period |`Data Disk Read Bytes/sec` |BytesPerSecond |Average |`LUN`|PT1M |Yes|
|**Data Disk Read Operations/Sec**<br><br>Read IOPS from a single disk during monitoring period |`Data Disk Read Operations/Sec` |CountPerSecond |Average |`LUN`|PT1M |Yes|
|**Data Disk Target Bandwidth**<br><br>Baseline bytes per second throughput Data Disk can achieve without bursting |`Data Disk Target Bandwidth` |Count |Average |`LUN`|PT1M |Yes|
|**Data Disk Target IOPS**<br><br>Baseline IOPS Data Disk can achieve without bursting |`Data Disk Target IOPS` |Count |Average |`LUN`|PT1M |Yes|
|**Data Disk Used Burst BPS Credits Percentage**<br><br>Percentage of Data Disk burst bandwidth credits used so far |`Data Disk Used Burst BPS Credits Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**Data Disk Used Burst IO Credits Percentage**<br><br>Percentage of Data Disk burst I/O credits used so far |`Data Disk Used Burst IO Credits Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**Data Disk Write Bytes/Sec**<br><br>Bytes/Sec written to a single disk during monitoring period |`Data Disk Write Bytes/sec` |BytesPerSecond |Average |`LUN`|PT1M |Yes|
|**Data Disk Write Operations/Sec**<br><br>Write IOPS from a single disk during monitoring period |`Data Disk Write Operations/Sec` |CountPerSecond |Average |`LUN`|PT1M |Yes|
|**Disk Read Bytes**<br><br>Bytes read from disk during monitoring period |`Disk Read Bytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Disk Read Operations/Sec**<br><br>Disk Read IOPS |`Disk Read Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Disk Write Bytes**<br><br>Bytes written to disk during monitoring period |`Disk Write Bytes` |Bytes |Total |\<none\>|PT1M |Yes|
|**Disk Write Operations/Sec**<br><br>Disk Write IOPS |`Disk Write Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Inbound Flows**<br><br>Inbound Flows are number of current flows in the inbound direction (traffic going into the VM) |`Inbound Flows` |Count |Average |\<none\>|PT1M |Yes|
|**Inbound Flows Maximum Creation Rate**<br><br>The maximum creation rate of inbound flows (traffic going into the VM) |`Inbound Flows Maximum Creation Rate` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Network In Billable (Deprecated)**<br><br>The number of billable bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic) (Deprecated) |`Network In` |Bytes |Total |\<none\>|PT1M |Yes|
|**Network In Total**<br><br>The number of bytes received on all network interfaces by the Virtual Machine(s) (Incoming Traffic) |`Network In Total` |Bytes |Total |\<none\>|PT1M |Yes|
|**Network Out Billable (Deprecated)**<br><br>The number of billable bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic) (Deprecated) |`Network Out` |Bytes |Total |\<none\>|PT1M |Yes|
|**Network Out Total**<br><br>The number of bytes out on all network interfaces by the Virtual Machine(s) (Outgoing Traffic) |`Network Out Total` |Bytes |Total |\<none\>|PT1M |Yes|
|**OS Disk Bandwidth Consumed Percentage**<br><br>Percentage of operating system disk bandwidth consumed per minute. Only available on VM series that support premium storage. |`OS Disk Bandwidth Consumed Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**OS Disk IOPS Consumed Percentage**<br><br>Percentage of operating system disk I/Os consumed per minute. Only available on VM series that support premium storage. |`OS Disk IOPS Consumed Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**OS Disk Latency (Preview)**<br><br>Average time to complete each IO during monitoring period for OS Disk. Values are in milliseconds. |`OS Disk Latency` |Milliseconds |Average |\<none\>|PT1M |Yes|
|**OS Disk Max Burst Bandwidth**<br><br>Maximum bytes per second throughput OS Disk can achieve with bursting |`OS Disk Max Burst Bandwidth` |Count |Average |`LUN`|PT1M |Yes|
|**OS Disk Max Burst IOPS**<br><br>Maximum IOPS OS Disk can achieve with bursting |`OS Disk Max Burst IOPS` |Count |Average |`LUN`|PT1M |Yes|
|**OS Disk Queue Depth**<br><br>OS Disk Queue Depth(or Queue Length) |`OS Disk Queue Depth` |Count |Average |\<none\>|PT1M |Yes|
|**OS Disk Read Bytes/Sec**<br><br>Bytes/Sec read from a single disk during monitoring period for OS disk |`OS Disk Read Bytes/sec` |BytesPerSecond |Average |\<none\>|PT1M |Yes|
|**OS Disk Read Operations/Sec**<br><br>Read IOPS from a single disk during monitoring period for OS disk |`OS Disk Read Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**OS Disk Target Bandwidth**<br><br>Baseline bytes per second throughput OS Disk can achieve without bursting |`OS Disk Target Bandwidth` |Count |Average |`LUN`|PT1M |Yes|
|**OS Disk Target IOPS**<br><br>Baseline IOPS OS Disk can achieve without bursting |`OS Disk Target IOPS` |Count |Average |`LUN`|PT1M |Yes|
|**OS Disk Used Burst BPS Credits Percentage**<br><br>Percentage of OS Disk burst bandwidth credits used so far |`OS Disk Used Burst BPS Credits Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**OS Disk Used Burst IO Credits Percentage**<br><br>Percentage of OS Disk burst I/O credits used so far |`OS Disk Used Burst IO Credits Percentage` |Percent |Average |`LUN`|PT1M |Yes|
|**OS Disk Write Bytes/Sec**<br><br>Bytes/Sec written to a single disk during monitoring period for OS disk |`OS Disk Write Bytes/sec` |BytesPerSecond |Average |\<none\>|PT1M |Yes|
|**OS Disk Write Operations/Sec**<br><br>Write IOPS from a single disk during monitoring period for OS disk |`OS Disk Write Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Outbound Flows**<br><br>Outbound Flows are number of current flows in the outbound direction (traffic going out of the VM) |`Outbound Flows` |Count |Average |\<none\>|PT1M |Yes|
|**Outbound Flows Maximum Creation Rate**<br><br>The maximum creation rate of outbound flows (traffic going out of the VM) |`Outbound Flows Maximum Creation Rate` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Percentage CPU**<br><br>The percentage of allocated compute units that are currently in use by the Virtual Machine(s) |`Percentage CPU` |Percent |Average |\<none\>|PT1M |Yes|
|**Premium Data Disk Cache Read Hit**<br><br>Premium Data Disk Cache Read Hit |`Premium Data Disk Cache Read Hit` |Percent |Average |`LUN`|PT1M |Yes|
|**Premium Data Disk Cache Read Miss**<br><br>Premium Data Disk Cache Read Miss |`Premium Data Disk Cache Read Miss` |Percent |Average |`LUN`|PT1M |Yes|
|**Premium OS Disk Cache Read Hit**<br><br>Premium OS Disk Cache Read Hit |`Premium OS Disk Cache Read Hit` |Percent |Average |\<none\>|PT1M |Yes|
|**Premium OS Disk Cache Read Miss**<br><br>Premium OS Disk Cache Read Miss |`Premium OS Disk Cache Read Miss` |Percent |Average |\<none\>|PT1M |Yes|
|**Temp Disk Latency (Preview)**<br><br>Average time to complete each IO during monitoring period for Temp Disk. Values are in milliseconds. |`Temp Disk Latency` |Milliseconds |Average |\<none\>|PT1M |Yes|
|**Temp Disk Queue Depth**<br><br>Temp Disk Queue Depth(or Queue Length). |`Temp Disk Queue Depth` |Count |Average |\<none\>|PT1M |Yes|
|**Temp Disk Read Bytes/Sec**<br><br>Bytes/Sec read from a single disk during monitoring period for Temp Disk. |`Temp Disk Read Bytes/sec` |BytesPerSecond |Average |\<none\>|PT1M |Yes|
|**Temp Disk Read Operations/Sec**<br><br>Read IOPS from a single disk during monitoring period for Temp Disk. |`Temp Disk Read Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**Temp Disk Write Bytes/Sec**<br><br>Bytes/Sec written to a single disk during monitoring period for Temp Disk. |`Temp Disk Write Bytes/sec` |BytesPerSecond |Average |\<none\>|PT1M |Yes|
|**Temp Disk Write Operations/Sec**<br><br>Write IOPS from a single disk during monitoring period for Temp Disk. |`Temp Disk Write Operations/Sec` |CountPerSecond |Average |\<none\>|PT1M |Yes|
|**VM Cached Bandwidth Consumed Percentage**<br><br>Percentage of cached disk bandwidth consumed by the VM. Only available on VM series that support premium storage. |`VM Cached Bandwidth Consumed Percentage` |Percent |Average |\<none\>|PT1M |Yes|
|**VM Cached IOPS Consumed Percentage**<br><br>Percentage of cached disk IOPS consumed by the VM. Only available on VM series that support premium storage. |`VM Cached IOPS Consumed Percentage` |Percent |Average |\<none\>|PT1M |Yes|
|**VM Cached Used Burst BPS Credits Percentage**<br><br>Percentage of Cached Burst BPS Credits used by the VM. |`VM Local Used Burst BPS Credits Percentage` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**VM Cached Used Burst IO Credits Percentage**<br><br>Percentage of Cached Burst IO Credits used by the VM. |`VM Local Used Burst IO Credits Percentage` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**VM Uncached Used Burst BPS Credits Percentage**<br><br>Percentage of Uncached Burst BPS Credits used by the VM. |`VM Remote Used Burst BPS Credits Percentage` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**VM Uncached Used Burst IO Credits Percentage**<br><br>Percentage of Uncached Burst IO Credits used by the VM. |`VM Remote Used Burst IO Credits Percentage` |Percent |Average, Minimum, Maximum |\<none\>|PT1M |Yes|
|**VM Uncached Bandwidth Consumed Percentage**<br><br>Percentage of uncached disk bandwidth consumed by the VM. Only available on VM series that support premium storage. |`VM Uncached Bandwidth Consumed Percentage` |Percent |Average |\<none\>|PT1M |Yes|
|**VM Uncached IOPS Consumed Percentage**<br><br>Percentage of uncached disk IOPS consumed by the VM. Only available on VM series that support premium storage. |`VM Uncached IOPS Consumed Percentage` |Percent |Average |\<none\>|PT1M |Yes|
|**VM Availability Metric (Preview)**<br><br>Measure of Availability of Virtual machines over time. |`VmAvailabilityMetric` |Count |Average, Minimum, Maximum |\<none\>|PT1M |Yes|