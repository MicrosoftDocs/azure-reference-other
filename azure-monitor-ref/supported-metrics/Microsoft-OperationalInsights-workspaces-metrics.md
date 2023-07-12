---
title: Supported metrics - Microsoft.OperationalInsights/workspaces
description: Reference for Microsoft.OperationalInsights/workspaces metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.OperationalInsights/workspaces  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.OperationalInsights/workspaces resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|AvailabilityRate_Query<p><p>User query success rate for this workspace. |`AvailabilityRate_Query` |Percent |Average |IsUserQuery |No|
|% Available Memory<p><p>Average_% Available Memory. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Available Memory` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Available Swap Space<p><p>Average_% Available Swap Space. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Available Swap Space` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Committed Bytes In Use<p><p>Average_% Committed Bytes In Use. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Committed Bytes In Use` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% DPC Time<p><p>Average_% DPC Time. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% DPC Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Free Inodes<p><p>Average_% Free Inodes. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Free Inodes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Free Space<p><p>Average_% Free Space. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Free Space` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Idle Time<p><p>Average_% Idle Time. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Idle Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Interrupt Time<p><p>Average_% Interrupt Time. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Interrupt Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% IO Wait Time<p><p>Average_% IO Wait Time. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% IO Wait Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Nice Time<p><p>Average_% Nice Time. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Nice Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Privileged Time<p><p>Average_% Privileged Time. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Privileged Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Processor Time<p><p>Average_% Processor Time. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Processor Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Used Inodes<p><p>Average_% Used Inodes. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Used Inodes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Used Memory<p><p>Average_% Used Memory. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Used Memory` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Used Space<p><p>Average_% Used Space. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Used Space` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% Used Swap Space<p><p>Average_% Used Swap Space. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% Used Swap Space` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|% User Time<p><p>Average_% User Time. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_% User Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Available MBytes<p><p>Average_Available MBytes. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Available MBytes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Available MBytes Memory<p><p>Average_Available MBytes Memory. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Available MBytes Memory` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Available MBytes Swap<p><p>Average_Available MBytes Swap. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Available MBytes Swap` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Avg. Disk sec/Read<p><p>Average_Avg. Disk sec/Read. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Avg. Disk sec/Read` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Avg. Disk sec/Transfer<p><p>Average_Avg. Disk sec/Transfer. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Avg. Disk sec/Transfer` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Avg. Disk sec/Write<p><p>Average_Avg. Disk sec/Write. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric).  |`Average_Avg. Disk sec/Write` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Bytes Received/sec<p><p>Average_Bytes Received/sec. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Bytes Received/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Bytes Sent/sec<p><p>Average_Bytes Sent/sec. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Bytes Sent/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Bytes Total/sec<p><p>Average_Bytes Total/sec. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Bytes Total/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Current Disk Queue Length<p><p>Average_Current Disk Queue Length. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Current Disk Queue Length` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Disk Read Bytes/sec<p><p>Average_Disk Read Bytes/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Disk Read Bytes/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Disk Reads/sec<p><p>Average_Disk Reads/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Disk Reads/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Disk Transfers/sec<p><p>Average_Disk Transfers/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Disk Transfers/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Disk Write Bytes/sec<p><p>Average_Disk Write Bytes/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Disk Write Bytes/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Disk Writes/sec<p><p>Average_Disk Writes/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Disk Writes/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Free Megabytes<p><p>Average_Free Megabytes. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Free Megabytes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Free Physical Memory<p><p>Average_Free Physical Memory. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric).  |`Average_Free Physical Memory` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Free Space in Paging Files<p><p>Average_Free Space in Paging Files. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Free Space in Paging Files` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Free Virtual Memory<p><p>Average_Free Virtual Memory. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Free Virtual Memory` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Logical Disk Bytes/sec<p><p>Average_Logical Disk Bytes/sec. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Logical Disk Bytes/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Page Reads/sec<p><p>Average_Page Reads/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Page Reads/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Page Writes/sec<p><p>Average_Page Writes/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Page Writes/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Pages/sec<p><p>Average_Pages/sec. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Pages/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Pct Privileged Time<p><p>Average_Pct Privileged Time. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Pct Privileged Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Pct User Time<p><p>Average_Pct User Time. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Pct User Time` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Physical Disk Bytes/sec<p><p>Average_Physical Disk Bytes/sec. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Physical Disk Bytes/sec` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Processes<p><p>Average_Processes. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Processes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Processor Queue Length<p><p>Average_Processor Queue Length. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric).  |`Average_Processor Queue Length` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Size Stored In Paging Files<p><p>Average_Size Stored In Paging Files. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Size Stored In Paging Files` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Bytes<p><p>Average_Total Bytes. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Bytes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Bytes Received<p><p>Average_Total Bytes Received. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Bytes Received` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Bytes Transmitted<p><p>Average_Total Bytes Transmitted. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Bytes Transmitted` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Collisions<p><p>Average_Total Collisions. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Collisions` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Packets Received<p><p>Average_Total Packets Received. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Packets Received` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Packets Transmitted<p><p>Average_Total Packets Transmitted. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Packets Transmitted` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Rx Errors<p><p>Average_Total Rx Errors. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Rx Errors` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Total Tx Errors<p><p>Average_Total Tx Errors. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Total Tx Errors` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Uptime<p><p>Average_Uptime. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Uptime` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Used MBytes Swap Space<p><p>. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Used MBytes Swap Space` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Used Memory kBytes<p><p>Average_Used Memory kBytes. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Used Memory kBytes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Used Memory MBytes<p><p>Average_Used Memory MBytes. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Used Memory MBytes` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Users<p><p>Average_Users. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Users` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Virtual Shared Memory<p><p>Average_Virtual Shared Memory. Supported for: Linux. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Average_Virtual Shared Memory` |Count |Average |Computer, ObjectName, InstanceName, CounterPath, SourceSystem |Yes|
|Event<p><p>Event. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Event` |Count |Average |Source, EventLog, Computer, EventCategory, EventLevel, EventLevelName, EventID |Yes|
|Heartbeat<p><p>Heartbeat. Supported for: Linux, Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Heartbeat` |Count |Total |Computer, OSType, Version, SourceComputerId |Yes|
|Query Count<p><p>Total number of user queries for this workspace. |`Query Count` |Count |Count |IsUserQuery |No|
|Query Failure Count<p><p>Total number of failed user queries for this workspace. |`Query Failure Count` |Count |Count |IsUserQuery |No|
|Update<p><p>Update. Supported for: Windows. Part of [metric alerts for logs feature](https://aka.ms/am-log-to-metric). |`Update` |Count |Average |Computer, Product, Classification, UpdateState, Optional, Approved |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->