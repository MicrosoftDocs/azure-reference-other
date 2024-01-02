---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/02/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkCloud/bareMetalMachines, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**CPU Guest Usage**<p><p>CPU guest usage refers to the allocation and utilization of CPU resources by a guest operating system in a virtualized environment |`CpuUsageGuest` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Guest Nice Usage**<p><p>CPU guest nice usage refers to the CPU time used by low priority user level processes running on a guest operating system in a virtualized environment |`CpuUsageGuestNice` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage Idle**<p><p>CPU usage idle refers to the percentage of time that a CPU is not being used by any program |`CpuUsageIdle` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage IO Wait**<p><p>CPU usage iowait refers to the percentage of time that the CPU (or CPUs) were idle during which the system had pending disk I/O requests |`CpuUsageIowait` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage IRQ**<p><p>CPU usage IRQ refers to the CPU time used by hardware interrupt requests |`CpuUsageIrq` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage Nice**<p><p>CPU usage nice refers to the percentage of CPU time used by low priority user level processes |`CpuUsageNice` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage Soft IRQ**<p><p>CPU usage soft IRQ refers to the CPU time used by software interrupt requests |`CpuUsageSoftirq` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage Steal**<p><p>CPU usage steal, also known as steal time, is the percentage of time a virtual CPU waits for a real CPU while the hypervisor is servicing another virtual processor. |`CpuUsageSteal` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage System**<p><p>System CPU usage is the percentage of a processor core total working time that is used to process data |`CpuUsageSystem` |Count |Average |`Host`, `CPU`|PT1M |No|
|**CPU Usage User**<p><p>CPU usage user refers to the percentage of CPU time used by user space processes |`CpuUsageUser` |Count |Average |`Host`, `CPU`|PT1M |No|
|**Host Boot Seconds (Preview)**<p><p>Unix time of last boot |`HostBootTimeSeconds` |Seconds |Average |`Host`|PT1M |No|
|**Host Disk Reads Completed**<p><p>Disk reads completed by node |`HostDiskReadCompleted` |Count |Average |`Device`, `Host`|PT1M |No|
|**Host Disk Read Seconds (Preview)**<p><p>Disk read time by node |`HostDiskReadSeconds` |Seconds |Average |`Device`, `Host`|PT1M |No|
|**Total Number of Writes Completed**<p><p>Disk writes completed by node |`HostDiskWriteCompleted` |Count |Average |`Device`, `Host`|PT1M |No|
|**Host Disk Write Seconds (Preview)**<p><p>Disk write time by node |`HostDiskWriteSeconds` |Seconds |Average |`Device`, `Host`|PT1M |No|
|**Host DMI Info (Preview)**<p><p>Host Desktop Management Interface (DMI) environment information |`HostDmiInfo` |Unspecified |Count |`BiosDate`, `BiosRelease`, `BiosVendor`, `BiosVersion`, `BoardAssetTag`, `BoardName`, `BoardVendor`, `BoardVersion`, `ChassisAssetTag`, `ChassisVendor`, `ChassisVersion`, `Host`, `ProductFamily`, `ProductName`, `ProductSku`, `ProductUuid`, `ProductVersion`, `SystemVendor`|PT1M |No|
|**Host Entropy Available Bits (Preview)**<p><p>Available bits in node entropy |`HostEntropyAvailableBits` |Count |Average |`Host`|PT1M |No|
|**Host Filesystem Available Bytes**<p><p>Available filesystem size by node |`HostFilesystemAvailBytes` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|**Host Filesystem Device Errors**<p><p>Indicates if there was a problem getting information for the filesystem |`HostFilesystemDeviceError` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|**Host Filesystem Files**<p><p>Total number of permitted inodes |`HostFilesystemFiles` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|**Total Number of Free inodes**<p><p>Total number of free inodes |`HostFilesystemFilesFree` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|**Host Filesystem Read Only**<p><p>Indicates if the filesystem is readonly |`HostFilesystemReadOnly` |Unspecified |Count |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|**Host Filesystem Size In Bytes**<p><p>Filesystem size by node |`HostFilesystemSizeBytes` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|**Host Hardware Monitor Temp**<p><p>Hardware monitor for temperature (celsius) |`HostHwmonTempCelsius` |Count |Average |`Chip`, `Host`, `Sensor`|PT1M |No|
|**Host Hardware Monitor Temp Max**<p><p>Hardware monitor for maximum temperature (celsius) |`HostHwmonTempMax` |Count |Average |`Chip`, `Host`, `Sensor`|PT1M |No|
|**Average Load In 1 Minute (Preview)**<p><p>1 minute load average |`HostLoad1` |Count |Average |`Host`|PT1M |No|
|**Average Load In 15 Minutes (Preview)**<p><p>15 minute load average |`HostLoad15` |Count |Average |`Host`|PT1M |No|
|**Average load in 5 minutes (Preview)**<p><p>5 minute load average |`HostLoad5` |Count |Average |`Host`|PT1M |No|
|**Host Memory Available Bytes**<p><p>Available memory in bytes by node |`HostMemAvailBytes` |Count |Average |`Host`|PT1M |No|
|**Total Memory In Corrupted Pages**<p><p>Corrupted bytes in hardware by node |`HostMemHWCorruptedBytes` |Count |Average |`Host`|PT1M |No|
|**Host Memory Swap Free Bytes**<p><p>Total bytes of free swap memory by node |`HostMemSwapFreeBytes` |Bytes |Average |`Host`|PT1M |No|
|**Host Memory Swap Total Bytes**<p><p>Total bytes of swap memory by node |`HostMemSwapTotalBytes` |Bytes |Average |`Host`|PT1M |No|
|**Host Memory Total Bytes**<p><p>Total bytes of memory by node |`HostMemTotalBytes` |Bytes |Average |`Host`|PT1M |No|
|**Host Specific CPU Utilization (Preview)**<p><p>A counter metric that counts the number of seconds the CPU has been running in a particular mode |`HostSpecificCPUUtilization` |Seconds |Average |`Cpu`, `Host`, `Mode`|PT1M |No|
|**IDRAC Power Capacity Watts**<p><p>Power Capacity |`IdracPowerCapacityWatts` |Unspecified |Average |`Host`, `PSU`|PT1M |No|
|**IDRAC Power Input Watts**<p><p>Power Input |`IdracPowerInputWatts` |Unspecified |Average |`Host`, `PSU`|PT1M |No|
|**IDRAC Power On**<p><p>IDRAC Power On Status |`IdracPowerOn` |Unspecified |Count |`Host`|PT1M |No|
|**IDRAC Power Output Watts**<p><p>Power Output |`IdracPowerOutputWatts` |Unspecified |Average |`Host`, `PSU`|PT1M |No|
|**IDRAC Sensors Temperature**<p><p>IDRAC sensor temperature |`IdracSensorsTemperature` |Unspecified |Average |`Host`, `Name`, `Units`|PT1M |No|
|**Network Device Receive Errors**<p><p>Total network device errors received |`NcNodeNetworkReceiveErrsTotal` |Count |Average |`Hostname`, `Interface Name`|PT1M |No|
|**Network Device Transmit Errors**<p><p>Total network device errors transmitted |`NcNodeNetworkTransmitErrsTotal` |Count |Average |`Hostname`, `Interface Name`|PT1M |No|
|**Total CPUs Available to Nexus per NUMA**<p><p>Total number of CPUs available to Nexus per NUMA |`NcTotalCpusPerNuma` |Count |Average |`Hostname`, `NUMA Node`|PT1M |No|
|**CPUs per NUMA Allocated for Nexus K8s**<p><p>Total number of CPUs per NUMA allocated for Nexus Kubernetes and Tenant Workloads |`NcTotalWorkloadCpusAllocatedPerNuma` |Count |Average |`Hostname`, `NUMA Node`|PT1M |No|
|**CPUs per NUMA Available for Nexus K8s**<p><p>Total number of CPUs per NUMA available to Nexus Kubernetes and Tenant Workloads |`NcTotalWorkloadCpusAvailablePerNuma` |Count |Average |`Hostname`, `NUMA Node`|PT1M |No|
|**Node Bonding Active (Preview)**<p><p>Number of active interfaces per bonding interface |`NodeBondingActive` |Count |Average |`Master`|PT1M |No|
|**Node Memory Huge Pages Free (Preview)**<p><p>NUMA hugepages free by node |`NodeMemHugePagesFree` |Bytes |Average |`Host`, `Node`|PT1M |No|
|**Node Memory Huge Pages Total**<p><p>NUMA huge pages total by node |`NodeMemHugePagesTotal` |Bytes |Average |`Host`, `Node`|PT1M |No|
|**Node Memory NUMA (Free Memory)**<p><p>NUMA memory free |`NodeMemNumaFree` |Bytes |Average |`Host`, `Node`|PT1M |No|
|**Node Memory NUMA (Shared Memory)**<p><p>NUMA shared memory |`NodeMemNumaShem` |Bytes |Average |`Host`, `Node`|PT1M |No|
|**Node Memory NUMA (Used Memory)**<p><p>NUMA memory used |`NodeMemNumaUsed` |Bytes |Average |`Host`, `Node`|PT1M |No|
|**Node Network Carrier Changes**<p><p>Node network carrier changes |`NodeNetworkCarrierChanges` |Count |Average |`Device`, `Host`|PT1M |No|
|**Node Network Max Transmission**<p><p>Node network Maximum Transmission Unit (mtu_bytes) value of /sys/class/net/\<iface\> |`NodeNetworkMtuBytes` |Bytes |Average |`Device`, `Host`|PT1M |No|
|**Node Network Received Multicast Total**<p><p>Network device statistic receive_multicast |`NodeNetworkReceiveMulticastTotal` |Bytes |Average |`Device`, `Host`|PT1M |No|
|**Node Network Received Packets**<p><p>Network device statistic receive_packets |`NodeNetworkReceivePackets` |Count |Average |`Device`, `Host`|PT1M |No|
|**Node Network Speed Bytes**<p><p>speed_bytes value of /sys/class/net/\<iface\> |`NodeNetworkSpeedBytes` |Bytes |Average |`Device`, `Host`|PT1M |No|
|**Node Network Transmited Packets**<p><p>Network device statistic transmit_packets |`NodeNetworkTransmitPackets` |Count |Average |`Device`, `Host`|PT1M |No|
|**Node Network Up**<p><p>Value is 1 if operstate is 'up', 0 otherwise. |`NodeNetworkUp` |Count |Count |`Device`, `Host`|PT1M |No|
|**Node NVMe Info (Preview)**<p><p>Non-numeric data from /sys/class/nvme/\<device\>, value is always 1. Provides firmware, model, state and serial for a device |`NodeNvmeInfo` |Count |Count |`Device`, `State`|PT1M |No|
|**Node OS Info**<p><p>Node OS information |`NodeOsInfo` |Count |Count |`Host`, `Name`, `Version`|PT1M |No|
|**Node Processes State**<p><p>Maximum time error between the local system and reference clock |`NodeProcessesState` |Count |Average |`Host`, `State`|PT1M |No|
|**Node Timex Max Error Seconds**<p><p>Maximum time error between the local system and reference clock |`NodeTimexMaxErrorSeconds` |Seconds |Average |`Host`|PT1M |No|
|**Node Timex Offset Seconds**<p><p>Time offset in between the local system and reference clock |`NodeTimexOffsetSeconds` |Seconds |Average |`Host`|PT1M |No|
|**Node Timex Sync Status**<p><p>Is clock synchronized to a reliable server (1 = yes, 0 = no) |`NodeTimexSyncStatus` |Count |Average |`Host`|PT1M |No|
|**Node VM Out Of Memory Kill**<p><p>Information in /proc/vmstat pertaining to the field oom_kill |`NodeVmOomKill` |Count |Average |`Host`|PT1M |No|
|**Node VM PSWP In**<p><p>Information in /proc/vmstat pertaining to the field pswpin |`NodeVmstatPswpIn` |Count |Average |`Host`|PT1M |No|
|**Node VM PSWP Out**<p><p>Information in /proc/vmstat pertaining to the field pswpout |`NodeVmstatPswpout` |Count |Average |`Host`|PT1M |No|