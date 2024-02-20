---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Network/networkWatchers/connectionMonitors, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Avg. Round-trip Time (ms) (classic)**<br><br>Average network round-trip time (ms) for connectivity monitoring probes sent between source and destination |`AverageRoundtripMs` |MilliSeconds |Average |\<none\>|PT1M, PT1H |Yes|
|**Checks Failed Percent**<br><br>% of connectivity monitoring checks failed |`ChecksFailedPercent` |Percent |Average |`SourceAddress`, `SourceName`, `SourceResourceId`, `SourceType`, `Protocol`, `DestinationAddress`, `DestinationName`, `DestinationResourceId`, `DestinationType`, `DestinationPort`, `TestGroupName`, `TestConfigurationName`, `SourceIP`, `DestinationIP`, `SourceSubnet`, `DestinationSubnet`|PT1M, PT1H |Yes|
|**% Probes Failed (classic)**<br><br>% of connectivity monitoring probes failed |`ProbesFailedPercent` |Percent |Average |\<none\>|PT1M, PT1H |Yes|
|**Round-Trip Time (ms)**<br><br>Round-trip time in milliseconds for the connectivity monitoring checks |`RoundTripTimeMs` |MilliSeconds |Average |`SourceAddress`, `SourceName`, `SourceResourceId`, `SourceType`, `Protocol`, `DestinationAddress`, `DestinationName`, `DestinationResourceId`, `DestinationType`, `DestinationPort`, `TestGroupName`, `TestConfigurationName`, `SourceIP`, `DestinationIP`, `SourceSubnet`, `DestinationSubnet`|PT1M, PT1H |Yes|
|**Test Result**<br><br>Connection monitor test result |`TestResult` |Count |Average |`SourceAddress`, `SourceName`, `SourceResourceId`, `SourceType`, `Protocol`, `DestinationAddress`, `DestinationName`, `DestinationResourceId`, `DestinationType`, `DestinationPort`, `TestGroupName`, `TestConfigurationName`, `TestResultCriterion`, `SourceIP`, `DestinationIP`, `SourceSubnet`, `DestinationSubnet`|PT1M, PT1H |Yes|