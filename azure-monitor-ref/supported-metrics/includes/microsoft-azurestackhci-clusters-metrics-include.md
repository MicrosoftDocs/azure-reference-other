---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.azurestackhci/clusters, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Volume Latency Read**<p><p>Average latency of read operations from this volume. |`Cluster CSVFS\Avg. sec/Read` |Seconds |Minimum, Maximum, Average, Total |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Volume Latency Write**<p><p>Average latency of write operations to this volume. |`Cluster CSVFS\Avg. sec/Write` |Seconds |Minimum, Maximum, Average, Total |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Disk Read Bytes/Sec**<p><p>Quantity of data read from this volume per second. |`Cluster CSVFS\Read Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Disk Read Operations/Sec**<p><p>Number of read operations per second completed by this volume. |`Cluster CSVFS\Reads/sec` |CountPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Disk Write Bytes/Sec**<p><p>Quantity of data written to this volume per second. |`Cluster CSVFS\Write Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Disk Write Operations/Sec**<p><p>Number of write operations per second completed by this volume. |`Cluster CSVFS\Writes/sec` |CountPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Clusternode Storage Degraded**<p><p>Total number of failed or missing drives in the storage pool. |`Cluster Node Storage Degraded` |Bytes |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Percentage CPU Guest**<p><p>Percentage of processor time used for guest (virtual machine) demand. |`Clusternode CPU Usage Guest` |Percent |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Clusternode Csvcache Read Hit**<p><p>Cache hit PerSecond for read operations. |`Clusternode CsvCache Read Hit` |CountPerSecond |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Clusternode Csvcache Read Hitrate**<p><p>Cache hit rate for read operations. |`Clusternode Csvcache Read Hitrate` |Percent |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Clusternode Csvcache Read Miss**<p><p>Cache missPerSecond for read operations. |`Clusternode Csvcache Read Miss` |CountPerSecond |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Percentage Memory**<p><p>The allocated (not available) memory of the server. |`ClusterNode Memory Usage` |Percent |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Clusternode Memory Used**<p><p>The used memory of the server. |`Clusternode Memory Used` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Vm Memory Pressure**<p><p>The ratio of memory demanded by the virtual machine over memory allocated to the virtual machine. |`Hyper-V Dynamic Memory VM\Current Pressure` |Percent |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Vm Memory Total**<p><p>Total memory. |`Hyper-V Dynamic Memory VM\Guest Visible Physical Memory` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Percentage CPU**<p><p>The percentage of processor time that is not idle. |`Hyper-V Hypervisor Logical Processor\% Total Run Time` |Percent |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Percentage CPU Host**<p><p>Percentage of processor time used for host demand. |`Hyper-V Hypervisor Root Virtual Processor\% Guest Run Time` |Percent |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Vmnetworkadapter Network In/Sec**<p><p>Rate of data received by the virtual machine across all its virtual network adapters. |`Hyper-V Virtual Network Adapter\Bytes Received/sec` |BitsPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vmnetworkadapter Network Out/Sec**<p><p>Rate of data sent by the virtual machine across all its virtual network adapters. |`Hyper-V Virtual Network Adapter\Bytes Sent/sec` |BitsPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vmnetworkadapter Network In and Out/Sec**<p><p>Total rate of data received or sent by the virtual machine across all its virtual network adapters. |`Hyper-V Virtual Network Adapter\Bytes/sec` |BitsPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Latency Average**<p><p>Average latency of all operations to or from the virtual hard disk. |`Hyper-V Virtual Storage Device\Latency` |Seconds |Minimum, Maximum, Average, Total |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Read Bytes/Sec**<p><p>Quantity of data read from the virtual hard disk per second. |`Hyper-V Virtual Storage Device\Read Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Read Operations/Sec**<p><p>Number of read operations per second completed by the virtual hard disk. |`Hyper-V Virtual Storage Device\Read Operations/Sec` |CountPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Write Bytes/Sec**<p><p>Quantity of data written to the virtual hard disk per second. |`Hyper-V Virtual Storage Device\Write Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Write Operations/Sec**<p><p>Number of write operations per second completed by the virtual hard disk. |`Hyper-V Virtual Storage Device\Write Operations/Sec` |CountPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Clusternode Memory Available**<p><p>The available memory of the server. |`Memory\Available Bytes` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Netadapter Bandwidth Rdma Total**<p><p>Total rate of data received or sent over RDMA by the network adapter. |`Netadapter Bandwidth Rdma Total` |BytesPerSecond |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Network In/Sec**<p><p>Rate of data received by the network adapter |`Network Adapter\Bytes Received/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Network Out/Sec**<p><p>Rate of data sent by the network adapter. |`Network Adapter\Bytes Sent/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Network Total/Sec**<p><p>Total rate of data received or sent by the network adapter. |`Network Adapter\Bytes Total/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Clusternode Memory Total**<p><p>The total physical memory of the server. |`NUMA Node Memory\Total MBytes` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Percentage Memory Guest**<p><p>The memory allocated to guest (virtual machine) demand. |`Percentage Memory Guest` |Percent |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Percentage Memory Host**<p><p>The memory allocated to host demand. |`Percentage Memory Host` |Percent |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`|PT1M |Yes|
|**Physicaldisk Capacity Size Total**<p><p>The total storage capacity of the drive. |`Physicaldisk Capacity Size Total` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Capacity Size Used**<p><p>The used storage capacity of the drive. |`Physicaldisk Capacity Size Used` |Bytes |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Latency Read**<p><p>Average latency of read operations from the drive. |`PhysicalDisk\Avg. Disk sec/Read` |Seconds |Minimum, Maximum, Average, Total |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Latency Average**<p><p>Average latency of all operations to or from the drive. |`PhysicalDisk\Avg. Disk sec/Transfer` |Seconds |Minimum, Maximum, Average, Total |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Latency Write**<p><p>Average latency of write operations to the drive. |`PhysicalDisk\Avg. Disk sec/Write` |Seconds |Minimum, Maximum, Average, Total |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Read and Write**<p><p>Total quantity of data read from or written to the drive per second. |`PhysicalDisk\Disk Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Read Bytes/Sec**<p><p>Quantity of data read from the drive per second. |`physicaldisk\Disk Read Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Read Operations/Sec**<p><p>Number of read operations completed by the drive. |`physicaldisk\disk reads/sec` |CountPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Read and Write Operations/Sec**<p><p>Total number of read or write operations per second completed by the drive. |`physicaldisk\disk transfers/sec` |CountPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Write Bytes/Sec**<p><p>Quantity of data written to the drive per second. |`physicaldisk\Disk Write Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Physicaldisk Write Operations/Sec**<p><p>Number of write operations completed by the drive. |`physicaldisk\disk writes/sec` |CountPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Netadapter Bandwidth Rdma Inbound**<p><p>Rate of data received over RDMA by the network adapter. |`RDMA Activity\RDMA Inbound Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Netadapter Bandwidth Rdma Outbound**<p><p>Rate of data sent over RDMA by the network adapter. |`RDMA Activity\RDMA Outbound Bytes/sec` |BytesPerSecond |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Vhd Read and Write Operations/Sec**<p><p>Total number of read or write operations per second completed by the virtual hard disk. |`VHD IOPS Total` |CountPerSecond |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Size Current**<p><p>The current file size of the virtual hard disk, if dynamically expanding. If fixed, the series is not collected. |`VHD Size Current` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Size Maximum**<p><p>The maximum size of the virtual hard disk, if dynamically expanding. If fixed, the series is the size. |`VHD Size Maximum` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vhd Read and Write Bytes/Sec**<p><p>Total quantity of data read from or written to the virtual hard disk per second. |`VHD Throughput Total` |BytesPerSecond |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vm Percentage CPU**<p><p>Percentage the virtual machine is using of its host server's processor(s). |`Virtual Processor Guest Run Time` |Percent |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `Instance`|PT1M |Yes|
|**Vm Memory Assigned**<p><p>The quantity of memory assigned to the virtual machine. |`VM Assigned Memory` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Vm Memory Available**<p><p>The quantity of memory that remains available, of the amount assigned. |`VM Memory Available` |Bytes |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Vm Memory Maximum**<p><p>If using dynamic memory, this is the maximum quantity of memory that may be assigned to the virtual machine. |`vm memory maximum` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Vm Memory Minimum**<p><p>If using dynamic memory, this is the minimum quantity of memory that may be assigned to the virtual machine. |`vm memory minimum` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Vm Memory Startup**<p><p>The quantity of memory required for the virtual machine to start. |`Vm Memory Startup` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**VM Memory Used**<p><p>The used memory. |`VM Memory Used` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `Instance`, `LUN`|PT1M |Yes|
|**Disk Read and Write Operations/Sec**<p><p>Total number of read or write operations per second completed by this volume. |`Volume IOPS Total` |CountPerSecond |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Volume Latency Average**<p><p>Average latency of all operations to or from this volume. |`Volume Latency Average` |Seconds |Minimum, Maximum, Total, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Volume Size Available**<p><p>The available storage capacity of the volume. |`volume size available` |Bytes |Minimum, Maximum, Average, Total, Count |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Volume Size Total**<p><p>The total storage capacity of the volume. |`volume size total` |Bytes |Minimum, Maximum, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|
|**Disk Read and Write**<p><p>Total quantity of data read from or written to this volume per second. |`Volume Throughput Total` |BytesPerSecond |Minimum, Maximum, Total, Count, Average |`ClusterName`, `ClusterNodeName`, `LUN`|PT1M |Yes|