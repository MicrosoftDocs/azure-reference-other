---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.MobileNetwork/radioAccessNetworks, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Traffic|**Active Receive Time**<br><br>The actual time of receiving data on the access point during the last sampling interval. |`ActiveReceiveTime` |MilliSeconds |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Active Transmit Time**<br><br>The actual time of transmitted data by the access poiont during the last sampling interval. |`ActiveTransmitTime` |MilliSeconds |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Active Users**<br><br>Number of currently active users on the Access Point. |`ActiveUsers` |Count |Total |`APIdentifier`|PT1M |No|
|Traffic|**Availability Rate**<br><br>Percentage of the sampling interval time that the access point was available. |`AvailabilityRate` |Percent |Average |`APIdentifier`|PT1M |Yes|
|Traffic|**Attempted Connection Handovers**<br><br>Number of attempts made to handover connections on the access point during the last sampling interval. |`ConnectionHandoverAttempts` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Successful Connection Handovers**<br><br>Number of connection handovers on the access point during the last sampling interval. |`ConnectionHandoverSuccesses` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Additionally Established Connections**<br><br>Number of additional connections established on the access point during the last sampling interval. |`ConnectionsAdditionallyEstablished` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Connection Attempts**<br><br>Number of connection attempts on the access point during the last sampling interval. |`ConnectionsAttempted` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Abnormal Connection Terminations**<br><br>Number of abnormally terminated connections on the access point during the last sampling interval. |`ConnectionsDropped` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Connections Successfully Established**<br><br>Number of established connections on the access point during the last sampling interval. |`ConnectionsEstablished` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Initially Established Connections**<br><br>Number of connections that were initially established with the access point during the last sampling interval. |`ConnectionsInitiallyEstablished` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Re-Connection Attempts**<br><br>Number of re-connection attempts on the access point during the last sampling interval. |`ConnectionsReAttempted` |Count |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Connections Successfully Re-Established**<br><br>Number of connections re-established on the access point during the last sampling interval. |`ConnectionsReEstablished` |Count |Total |`APIdentifier`|PT1M |Yes|
|Derived Traffic|**Derived Connection Success Rate (CSR)**<br><br>Percentage of successful connections on the given access point. |`dConnectionSuccessRate` |Percent |Average |`APIdentifier`|PT1M |Yes|
|Derived Traffic|**Derived Mobility Success Rate (MSR)**<br><br>Percentage of successful handovers on the given access point. |`dMobilitySuccessRate` |Percent |Average |`APIdentifier`|PT1M |Yes|
|Traffic|**Downtime**<br><br>Number of seconds that the access point was down during the last sampling interval. |`Downtime` |Seconds |Total |`APIdentifier`|PT1M |Yes|
|Derived Traffic|**Derived Receive Throughput**<br><br>Throughput of received data on a given access point. |`dReceiveThroughput` |BitsPerSecond |Average |`APIdentifier`|PT1M |Yes|
|Derived Traffic|**Derived Transmit Throughput**<br><br>Throughput of transmitted data by a given access point. |`dTransmitThroughput` |BitsPerSecond |Average |`APIdentifier`|PT1M |Yes|
|Traffic|**Online Status**<br><br>Indicates if an access point was online during the whole sampling interval or not. The value 0 represents Offline and 1 represents Online. |`OnlineStatus` |Count |Total, Count, Maximum, Minimum |`APIdentifier`|PT1M |Yes|
|Traffic|**Receive Data Rate**<br><br>The rate at which the data was received on the access point during the last sampling interval. |`ReceiveDataRate` |BitsPerSecond |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Receive Volume**<br><br>Volume of received data on the access point during the last sampling interval. |`ReceiveVolume` |Bytes |Total |`APIdentifier`, `RANIdentifier`|PT1M |Yes|
|Traffic|**Transmit Data Rate**<br><br>The rate at which the data was transmitted by the access point during last sampling interval. |`TransmitDataRate` |BitsPerSecond |Total |`APIdentifier`|PT1M |Yes|
|Traffic|**Transmit Volume**<br><br>Volume of data transmitted by the access point during the last sampling interval. |`TransmitVolume` |Bytes |Total |`APIdentifier`, `RANIdentifier`|PT1M |Yes|