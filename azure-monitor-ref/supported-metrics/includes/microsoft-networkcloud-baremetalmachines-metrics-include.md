---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/23/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.NetworkCloud/bareMetalMachines, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|CPU|**CPU Guest Usage**<br><br>CPU guest usage refers to the allocation and utilization of CPU resources by a guest operating system in a virtualized environment |`CpuUsageGuest` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Guest Nice Usage**<br><br>CPU guest nice usage refers to the CPU time used by low priority user level processes running on a guest operating system in a virtualized environment |`CpuUsageGuestNice` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage Idle**<br><br>CPU usage idle refers to the percentage of time that a CPU is not being used by any program |`CpuUsageIdle` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage IO Wait**<br><br>CPU usage iowait refers to the percentage of time that the CPU (or CPUs) were idle during which the system had pending disk I/O requests |`CpuUsageIowait` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage IRQ**<br><br>CPU usage IRQ refers to the CPU time used by hardware interrupt requests |`CpuUsageIrq` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage Nice**<br><br>CPU usage nice refers to the percentage of CPU time used by low priority user level processes |`CpuUsageNice` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage Soft IRQ**<br><br>CPU usage soft IRQ refers to the CPU time used by software interrupt requests |`CpuUsageSoftirq` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage Steal**<br><br>CPU usage steal, also known as steal time, is the percentage of time a virtual CPU waits for a real CPU while the hypervisor is servicing another virtual processor. |`CpuUsageSteal` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage System**<br><br>System CPU usage is the percentage of a processor core total working time that is used to process data |`CpuUsageSystem` |Count |Average |`Host`, `CPU`|PT1M |No|
|CPU|**CPU Usage Total**<br><br>Total CPU usage is the percentage of a processor core total working time that is used to process data |`CpuUsageTotal` |Percent |Average |`Host`, `CPU`|PT1M |Yes|
|CPU|**CPU Usage User**<br><br>CPU usage user refers to the percentage of CPU time used by user space processes |`CpuUsageUser` |Count |Average |`Host`, `CPU`|PT1M |No|
|System|**Host Boot Seconds (Preview)**<br><br>Unix time of last boot |`HostBootTimeSeconds` |Seconds |Average |`Host`|PT1M |No|
|Disk|**Host Disk Reads Completed**<br><br>Disk reads completed by node |`HostDiskReadCompleted` |Count |Average |`Device`, `Host`|PT1M |No|
|Disk|**Host Disk Read Seconds (Preview)**<br><br>Disk read time by node |`HostDiskReadSeconds` |Seconds |Average |`Device`, `Host`|PT1M |No|
|Disk|**Total Number of Writes Completed**<br><br>Disk writes completed by node |`HostDiskWriteCompleted` |Count |Average |`Device`, `Host`|PT1M |No|
|Disk|**Host Disk Write Seconds (Preview)**<br><br>Disk write time by node |`HostDiskWriteSeconds` |Seconds |Average |`Device`, `Host`|PT1M |No|
|System|**Host DMI Info (Deprecated)**<br><br>Deprecated - Host Desktop Management Interface (DMI) environment information |`HostDmiInfo` |Unspecified |Count |`BiosDate`, `BiosRelease`, `BiosVendor`, `BiosVersion`, `BoardAssetTag`, `BoardName`, `BoardVendor`, `BoardVersion`, `ChassisAssetTag`, `ChassisVendor`, `ChassisVersion`, `Host`, `ProductFamily`, `ProductName`, `ProductSku`, `ProductUuid`, `ProductVersion`, `SystemVendor`|PT1M |No|
|System|**Host DMI Info**<br><br>Host Desktop Management Interface (DMI) environment information |`HostDmiInformation` |Unspecified |Count |`BiosDate`, `BiosRelease`, `BiosVendor`, `BiosVersion`, `BoardName`, `BoardVendor`, `BoardVersion`, `ChassisAssetTag`, `ChassisVendor`, `Host`, `ProductFamily`, `ProductName`, `ProductSku`, `SystemVendor`|PT1M |No|
|Filesystem|**Host Entropy Available Bits (Preview)**<br><br>Available bits in node entropy |`HostEntropyAvailableBits` |Count |Average |`Host`|PT1M |No|
|Filesystem|**Host Filesystem Available Bytes**<br><br>Available filesystem size by node |`HostFilesystemAvailBytes` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|Filesystem|**Host Filesystem Device Errors**<br><br>Indicates if there was a problem getting information for the filesystem |`HostFilesystemDeviceError` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|Filesystem|**Host Filesystem Files**<br><br>Total number of permitted inodes |`HostFilesystemFiles` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|Filesystem|**Total Number of Free inodes**<br><br>Total number of free inodes |`HostFilesystemFilesFree` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|Filesystem|**Host Filesystem Files Percent Free**<br><br>Percentage of permitted inodes free to be used |`HostFilesystemFilesPercentFree` |Percent |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|Filesystem|**Host Filesystem Read Only**<br><br>Indicates if the filesystem is readonly |`HostFilesystemReadOnly` |Unspecified |Count |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|Filesystem|**Host Filesystem Size In Bytes**<br><br>Filesystem size by node |`HostFilesystemSizeBytes` |Count |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|Filesystem|**Host Filesystem Usage In Percentage**<br><br>Percentage of used filesystem by node |`HostFilesystemUsage` |Percent |Average |`Device`, `FSType`, `Host`, `Mountpoint`|PT1M |No|
|HardwareMonitor|**Host Hardware Monitor Temp**<br><br>Hardware monitor for temperature (celsius) |`HostHwmonTempCelsius` |Count |Average |`Chip`, `Host`, `Sensor`|PT1M |No|
|HardwareMonitor|**Host Hardware Monitor Temp Max**<br><br>Hardware monitor for maximum temperature (celsius) |`HostHwmonTempMax` |Count |Average |`Chip`, `Host`, `Sensor`|PT1M |No|
|HardwareMonitor|**Host Hardware Inlet Temp**<br><br>Inlet temperature for a hardware node (celsius) |`HostInletTemp` |Count |Average |`Host`|PT1M |No|
|Memory|**Average Load In 1 Minute (Preview)**<br><br>1 minute load average |`HostLoad1` |Count |Average |`Host`|PT1M |No|
|Memory|**Average Load In 15 Minutes (Preview)**<br><br>15 minute load average |`HostLoad15` |Count |Average |`Host`|PT1M |No|
|Memory|**Average load in 5 minutes (Preview)**<br><br>5 minute load average |`HostLoad5` |Count |Average |`Host`|PT1M |No|
|Memory|**Host Memory Available Bytes**<br><br>Available memory in bytes by node |`HostMemAvailBytes` |Count |Average |`Host`|PT1M |No|
|Memory|**Memory Free Huge Pages**<br><br>Hugepages memory free on host |`HostMemHugePagesFree` |Bytes |Average |`Host`|PT1M |No|
|Memory|**Memory Total Huge Pages**<br><br>Huge pages total on host |`HostMemHugePagesTotal` |Bytes |Average |`Host`|PT1M |No|
|Memory|**Total Memory In Corrupted Pages**<br><br>Corrupted bytes in hardware by node |`HostMemHWCorruptedBytes` |Count |Average |`Host`|PT1M |No|
|Memory|**Host Memory Swap Available Percentage**<br><br>Percentage of available swap memory by node |`HostMemSwapAvailableSpace` |Percent |Average |`Host`|PT1M |No|
|Memory|**Host Memory Swap Free Bytes**<br><br>Total bytes of free swap memory by node |`HostMemSwapFreeBytes` |Bytes |Average |`Host`|PT1M |No|
|Memory|**Host Memory Swap Total Bytes**<br><br>Total bytes of swap memory by node |`HostMemSwapTotalBytes` |Bytes |Average |`Host`|PT1M |No|
|Memory|**Host Memory Total Bytes**<br><br>Total bytes of memory by node |`HostMemTotalBytes` |Bytes |Average |`Host`|PT1M |No|
|CPU|**Host Specific CPU Utilization (Preview)**<br><br>A counter metric that counts the number of seconds the CPU has been running in a particular mode |`HostSpecificCPUUtilization` |Seconds |Average |`Cpu`, `Host`, `Mode`|PT1M |No|
|HardwareMonitor|**IDRAC Power Capacity Watts**<br><br>Power Capacity |`IdracPowerCapacityWatts` |Unspecified |Average |`Host`, `PSU`|PT1M |No|
|HardwareMonitor|**IDRAC Power Input Watts**<br><br>Power Input |`IdracPowerInputWatts` |Unspecified |Average |`Host`, `PSU`|PT1M |No|
|HardwareMonitor|**IDRAC Power On**<br><br>IDRAC Power On Status |`IdracPowerOn` |Unspecified |Count |`Host`|PT1M |No|
|HardwareMonitor|**IDRAC Power Output Watts**<br><br>Power Output |`IdracPowerOutputWatts` |Unspecified |Average |`Host`, `PSU`|PT1M |No|
|HardwareMonitor|**IDRAC Sensors Temperature**<br><br>IDRAC sensor temperature |`IdracSensorsTemperature` |Unspecified |Average |`Host`, `Name`, `Units`|PT1M |No|
|Network|**Network Device Receive Errors**<br><br>Total network device errors received |`NcNodeNetworkReceiveErrsTotal` |Count |Average |`Hostname`, `Interface Name`|PT1M |No|
|Network|**Network Device Transmit Errors**<br><br>Total network device errors transmitted |`NcNodeNetworkTransmitErrsTotal` |Count |Average |`Hostname`, `Interface Name`|PT1M |No|
|CPU|**Total CPUs Available to Nexus per NUMA**<br><br>Total number of CPUs available to Nexus per NUMA |`NcTotalCpusPerNuma` |Count |Average |`Hostname`, `NUMA Node`|PT1M |No|
|CPU|**CPUs per NUMA Allocated for Nexus K8s**<br><br>Total number of CPUs per NUMA allocated for Nexus Kubernetes and Tenant Workloads |`NcTotalWorkloadCpusAllocatedPerNuma` |Count |Average |`Hostname`, `NUMA Node`|PT1M |No|
|CPU|**CPUs per NUMA Available for Nexus K8s**<br><br>Total number of CPUs per NUMA available to Nexus Kubernetes and Tenant Workloads |`NcTotalWorkloadCpusAvailablePerNuma` |Count |Average |`Hostname`, `NUMA Node`|PT1M |No|
|Network|**Node Bonding Active (Preview)**<br><br>Number of active interfaces per bonding interface |`NodeBondingActive` |Count |Average |`Master`|PT1M |No|
|Network|**Node Bond Aggregate ID Mismatch**<br><br>Indicates a mismatch in link-aggregator ids |`NodeBondingAggregateIdMismatch` |Count |Average |`Host`, `Interface`|PT1M |No|
|Memory|**Node Memory Huge Pages Free (Preview)**<br><br>NUMA hugepages free by node |`NodeMemHugePagesFree` |Bytes |Average |`Host`, `Node`|PT1M |No|
|Memory|**Node Memory Huge Pages Total**<br><br>NUMA huge pages total by node |`NodeMemHugePagesTotal` |Bytes |Average |`Host`, `Node`|PT1M |No|
|Memory|**Node Memory NUMA (Free Memory)**<br><br>NUMA memory free |`NodeMemNumaFree` |Bytes |Average |`Host`, `Node`|PT1M |No|
|Memory|**Node Memory NUMA (Shared Memory)**<br><br>NUMA shared memory |`NodeMemNumaShem` |Bytes |Average |`Host`, `Node`|PT1M |No|
|Memory|**Node Memory NUMA (Used Memory)**<br><br>NUMA memory used |`NodeMemNumaUsed` |Bytes |Average |`Host`, `Node`|PT1M |No|
|Network|**Node Network Carrier Changes**<br><br>Node network carrier changes |`NodeNetworkCarrierChanges` |Count |Average |`Device`, `Host`|PT1M |No|
|Network|**Node Network Max Transmission**<br><br>Node network Maximum Transmission Unit (mtu_bytes) value of /sys/class/net/\<iface\> |`NodeNetworkMtuBytes` |Bytes |Average |`Device`, `Host`|PT1M |No|
|Network|**Node Network Received Multicast Total**<br><br>Network device statistic receive_multicast |`NodeNetworkReceiveMulticastTotal` |Bytes |Average |`Device`, `Host`|PT1M |No|
|Network|**Node Network Received Packets**<br><br>Network device statistic receive_packets |`NodeNetworkReceivePackets` |Count |Average |`Device`, `Host`|PT1M |No|
|Network|**Node Network Speed Bytes**<br><br>speed_bytes value of /sys/class/net/\<iface\> |`NodeNetworkSpeedBytes` |Bytes |Average |`Device`, `Host`|PT1M |No|
|Network|**Node Network Up**<br><br>Value is 1 if operstate is 'up', 0 otherwise. |`NodeNetworkStatus` |Count |Count |`Device`, `Host`|PT1M |No|
|Network|**Node Network Transmited Packets**<br><br>Network device statistic transmit_packets |`NodeNetworkTransmitPackets` |Count |Average |`Device`, `Host`|PT1M |No|
|Network|**Node Network Up - (Deprecated)**<br><br>Deprecated - Value is 1 if operstate is 'up', 0 otherwise. |`NodeNetworkUp` |Count |Count |`Device`, `Host`|PT1M |No|
|System|**Node NTP Leap**<br><br>Monitoring time sync with raw leap flag |`NodeNtpLeap` |Count |Average |`Host`|PT1M |No|
|System|**Node NTP RTT**<br><br>Round-trip time (seconds) from node exporter collector to local NTP daemon |`NodeNtpRtt` |Seconds |Average |`Host`|PT1M |No|
|System|**Node NTP Sanity**<br><br>NTP daemon health |`NodeNtpSanity` |Count |Average |`Host`|PT1M |No|
|System|**Node NTP Stratum**<br><br>Denotes clock synchronization of the local NTP daemon |`NodeNtpStratum` |Count |Average |`Host`|PT1M |No|
|Disk|**Node NVMe Info (Preview)**<br><br>Non-numeric data from /sys/class/nvme/\<device\>, value is always 1. Provides firmware, model, state and serial for a device |`NodeNvmeInfo` |Count |Count |`Device`, `State`|PT1M |No|
|System|**Node OS Info**<br><br>Node OS information |`NodeOsInfo` |Count |Count |`Host`, `Name`, `Version`|PT1M |No|
|System|**Node Processes State - (Deprecated)**<br><br>Deprecated - Maximum time error between the local system and reference clock |`NodeProcessesState` |Count |Average |`Host`, `State`|PT1M |No|
|System|**Node Processes State**<br><br>Maximum time error between the local system and reference clock |`NodeProcessState` |Count |Average |`Host`, `State`|PT1M |No|
|System|**Node Timex Max Error Seconds**<br><br>Maximum time error between the local system and reference clock |`NodeTimexMaxErrorSeconds` |Seconds |Average |`Host`|PT1M |No|
|System|**Node Timex Offset Seconds**<br><br>Time offset in between the local system and reference clock |`NodeTimexOffsetSeconds` |Seconds |Average |`Host`|PT1M |No|
|System|**Node Timex Sync Status**<br><br>Is clock synchronized to a reliable server (1 = yes, 0 = no) |`NodeTimexSyncStatus` |Count |Average |`Host`|PT1M |No|
|VM Stat|**Node VM Out Of Memory Kill**<br><br>Information in /proc/vmstat pertaining to the field oom_kill |`NodeVmOomKill` |Count |Average |`Host`|PT1M |No|
|VM Stat|**Node VM PSWP In**<br><br>Information in /proc/vmstat pertaining to the field pswpin |`NodeVmstatPswpIn` |Count |Average |`Host`|PT1M |No|
|VM Stat|**Node VM PSWP Out**<br><br>Information in /proc/vmstat pertaining to the field pswpout |`NodeVmstatPswpout` |Count |Average |`Host`|PT1M |No|