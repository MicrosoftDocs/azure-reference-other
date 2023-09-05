---
title: Supported metrics - Microsoft.azurestackhci/clusters
description: Reference for Microsoft.azurestackhci/clusters metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/04/2023
---
# Supported metrics for Microsoft.azurestackhci/clusters  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.azurestackhci/clusters resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Volume Latency Read<p><p>Average latency of read operations from this volume. |`Cluster CSVFS\Avg. sec/Read` |Seconds |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Volume Latency Write<p><p>Average latency of write operations to this volume. |`Cluster CSVFS\Avg. sec/Write` |Seconds |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Disk Read Bytes/Sec<p><p>Quantity of data read from this volume per second. |`Cluster CSVFS\Read Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Disk Read Operations/Sec<p><p>Number of read operations per second completed by this volume. |`Cluster CSVFS\Reads/sec` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Disk Write Bytes/Sec<p><p>Quantity of data written to this volume per second. |`Cluster CSVFS\Write Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Disk Write Operations/Sec<p><p>Number of write operations per second completed by this volume. |`Cluster CSVFS\Writes/sec` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Clusternode Storage Degraded<p><p>Total number of failed or missing drives in the storage pool. |`Cluster Node Storage Degraded` |Bytes |Total |ClusterName, ClusterNodeName |Yes|
|Percentage CPU Guest<p><p>Percentage of processor time used for guest (virtual machine) demand. |`Clusternode CPU Usage Guest` |Percent |Maximum |ClusterName, ClusterNodeName |Yes|
|Clusternode Csvcache Read Hit<p><p>Cache hit PerSecond for read operations. |`Clusternode CsvCache Read Hit` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Clusternode Csvcache Read Hitrate<p><p>Cache hit rate for read operations. |`Clusternode Csvcache Read Hitrate` |Percent |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Clusternode Csvcache Read Miss<p><p>Cache missPerSecond for read operations. |`Clusternode Csvcache Read Miss` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Percentage Memory<p><p>The allocated (not available) memory of the server. |`ClusterNode Memory Usage` |Percent |Maximum |ClusterName, ClusterNodeName |Yes|
|Clusternode Memory Used<p><p>The used memory of the server. |`Clusternode Memory Used` |Bytes |Maximum |ClusterName, ClusterNodeName |Yes|
|Vm Memory Pressure<p><p>The ratio of memory demanded by the virtual machine over memory allocated to the virtual machine. |`Hyper-V Dynamic Memory VM\Current Pressure` |Percent |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Vm Memory Total<p><p>Total memory. |`Hyper-V Dynamic Memory VM\Guest Visible Physical Memory` |Bytes |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Percentage CPU<p><p>The percentage of processor time that is not idle. |`Hyper-V Hypervisor Logical Processor\% Total Run Time` |Percent |Maximum |ClusterName, ClusterNodeName |Yes|
|Percentage CPU Host<p><p>Percentage of processor time used for host demand. |`Hyper-V Hypervisor Root Virtual Processor\% Guest Run Time` |Percent |Maximum |ClusterName, ClusterNodeName |Yes|
|Vmnetworkadapter Network In/Sec<p><p>Rate of data received by the virtual machine across all its virtual network adapters. |`Hyper-V Virtual Network Adapter\Bytes Received/sec` |BitsPerSecond |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vmnetworkadapter Network Out/Sec<p><p>Rate of data sent by the virtual machine across all its virtual network adapters. |`Hyper-V Virtual Network Adapter\Bytes Sent/sec` |BitsPerSecond |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vmnetworkadapter Network In and Out/Sec<p><p>Total rate of data received or sent by the virtual machine across all its virtual network adapters. |`Hyper-V Virtual Network Adapter\Bytes/sec` |BitsPerSecond |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Latency Average<p><p>Average latency of all operations to or from the virtual hard disk. |`Hyper-V Virtual Storage Device\Latency` |Seconds |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Read Bytes/Sec<p><p>Quantity of data read from the virtual hard disk per second. |`Hyper-V Virtual Storage Device\Read Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Read Operations/Sec<p><p>Number of read operations per second completed by the virtual hard disk. |`Hyper-V Virtual Storage Device\Read Operations/Sec` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Write Bytes/Sec<p><p>Quantity of data written to the virtual hard disk per second. |`Hyper-V Virtual Storage Device\Write Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Write Operations/Sec<p><p>Number of write operations per second completed by the virtual hard disk. |`Hyper-V Virtual Storage Device\Write Operations/Sec` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Clusternode Memory Available<p><p>The available memory of the server. |`Memory\Available Bytes` |Bytes |Maximum |ClusterName, ClusterNodeName |Yes|
|Netadapter Bandwidth Rdma Total<p><p>Total rate of data received or sent over RDMA by the network adapter. |`Netadapter Bandwidth Rdma Total` |BytesPerSecond |Total |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Network In/Sec<p><p>Rate of data received by the network adapter |`Network Adapter\Bytes Received/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Network Out/Sec<p><p>Rate of data sent by the network adapter. |`Network Adapter\Bytes Sent/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Network Total/Sec<p><p>Total rate of data received or sent by the network adapter. |`Network Adapter\Bytes Total/sec` |BytesPerSecond |Total |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Clusternode Memory Total<p><p>The total physical memory of the server. |`NUMA Node Memory\Total MBytes` |Bytes |Total |ClusterName, ClusterNodeName |Yes|
|Percentage Memory Guest<p><p>The memory allocated to guest (virtual machine) demand. |`Percentage Memory Guest` |Percent |Maximum |ClusterName, ClusterNodeName |Yes|
|Percentage Memory Host<p><p>The memory allocated to host demand. |`Percentage Memory Host` |Percent |Maximum |ClusterName, ClusterNodeName |Yes|
|Physicaldisk Capacity Size Total<p><p>The total storage capacity of the drive. |`Physicaldisk Capacity Size Total` |Bytes |Total |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Capacity Size Used<p><p>The used storage capacity of the drive. |`Physicaldisk Capacity Size Used` |Bytes |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Latency Read<p><p>Average latency of read operations from the drive. |`PhysicalDisk\Avg. Disk sec/Read` |Seconds |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Latency Average<p><p>Average latency of all operations to or from the drive. |`PhysicalDisk\Avg. Disk sec/Transfer` |Seconds |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Latency Write<p><p>Average latency of write operations to the drive. |`PhysicalDisk\Avg. Disk sec/Write` |Seconds |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Read and Write<p><p>Total quantity of data read from or written to the drive per second. |`PhysicalDisk\Disk Bytes/sec` |BytesPerSecond |Total |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Read Bytes/Sec<p><p>Quantity of data read from the drive per second. |`physicaldisk\Disk Read Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Read Operations/Sec<p><p>Number of read operations completed by the drive. |`physicaldisk\disk reads/sec` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Read and Write Operations/Sec<p><p>Total number of read or write operations per second completed by the drive. |`physicaldisk\disk transfers/sec` |CountPerSecond |Total |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Write Bytes/Sec<p><p>Quantity of data written to the drive per second. |`physicaldisk\Disk Write Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Physicaldisk Write Operations/Sec<p><p>Number of write operations completed by the drive. |`physicaldisk\disk writes/sec` |CountPerSecond |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Netadapter Bandwidth Rdma Inbound<p><p>Rate of data received over RDMA by the network adapter. |`RDMA Activity\RDMA Inbound Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Netadapter Bandwidth Rdma Outbound<p><p>Rate of data sent over RDMA by the network adapter. |`RDMA Activity\RDMA Outbound Bytes/sec` |BytesPerSecond |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Vhd Read and Write Operations/Sec<p><p>Total number of read or write operations per second completed by the virtual hard disk. |`VHD IOPS Total` |CountPerSecond |Total |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Size Current<p><p>The current file size of the virtual hard disk, if dynamically expanding. If fixed, the series is not collected. |`VHD Size Current` |Bytes |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Size Maximum<p><p>The maximum size of the virtual hard disk, if dynamically expanding. If fixed, the series is the size. |`VHD Size Maximum` |Bytes |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vhd Read and Write Bytes/Sec<p><p>Total quantity of data read from or written to the virtual hard disk per second. |`VHD Throughput Total` |BytesPerSecond |Total |ClusterName, ClusterNodeName, Instance |Yes|
|Vm Memory Assigned<p><p>The quantity of memory assigned to the virtual machine. |`VM Assigned Memory` |Bytes |Total |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Vm Percentage CPU<p><p>Percentage the virtual machine is using of its host server's processor(s). |`VM CPU Usage` |Percent |Maximum |ClusterName, ClusterNodeName, Instance |Yes|
|Vm Memory Available<p><p>The quantity of memory that remains available, of the amount assigned. |`VM Memory Available` |Bytes |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Vm Memory Maximum<p><p>If using dynamic memory, this is the maximum quantity of memory that may be assigned to the virtual machine. |`vm memory maximum` |Bytes |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Vm Memory Minimum<p><p>If using dynamic memory, this is the minimum quantity of memory that may be assigned to the virtual machine. |`vm memory minimum` |Bytes |Minimum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Vm Memory Startup<p><p>The quantity of memory required for the virtual machine to start. |`Vm Memory Startup` |Bytes |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|VM Memory Used<p><p>The used memory. |`VM Memory Used` |Bytes |Maximum |ClusterName, ClusterNodeName, Instance, LUN |Yes|
|Disk Read and Write Operations/Sec<p><p>Total number of read or write operations per second completed by this volume. |`Volume IOPS Total` |CountPerSecond |Total |ClusterName, ClusterNodeName, LUN |Yes|
|Volume Latency Average<p><p>Average latency of all operations to or from this volume. |`Volume Latency Average` |Seconds |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Volume Size Available<p><p>The available storage capacity of the volume. |`volume size available` |Bytes |Maximum |ClusterName, ClusterNodeName, LUN |Yes|
|Volume Size Total<p><p>The total storage capacity of the volume. |`volume size total` |Bytes |Total |ClusterName, ClusterNodeName, LUN |Yes|
|Disk Read and Write<p><p>Total quantity of data read from or written to this volume per second. |`Volume Throughput Total` |BytesPerSecond |Total |ClusterName, ClusterNodeName, LUN |Yes|


<!--Gen Date:  Mon Sep 04 2023 13:11:00 GMT+0300 (Israel Daylight Time)-->