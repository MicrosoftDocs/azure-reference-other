---
title: Supported metrics - Microsoft.Network/networkWatchers/connectionMonitors
description: Reference for Microsoft.Network/networkWatchers/connectionMonitors metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Network/networkWatchers/connectionMonitors  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Network/networkWatchers/connectionMonitors resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Avg. Round-trip Time (ms) (classic)<p><p>Average network round-trip time (ms) for connectivity monitoring probes sent between source and destination |`AverageRoundtripMs` |MilliSeconds |Average |No Dimensions |Yes|
|Checks Failed Percent<p><p>% of connectivity monitoring checks failed |`ChecksFailedPercent` |Percent |Average |SourceAddress, SourceName, SourceResourceId, SourceType, Protocol, DestinationAddress, DestinationName, DestinationResourceId, DestinationType, DestinationPort, TestGroupName, TestConfigurationName, SourceIP, DestinationIP, SourceSubnet, DestinationSubnet |Yes|
|% Probes Failed (classic)<p><p>% of connectivity monitoring probes failed |`ProbesFailedPercent` |Percent |Average |No Dimensions |Yes|
|Round-Trip Time (ms)<p><p>Round-trip time in milliseconds for the connectivity monitoring checks |`RoundTripTimeMs` |MilliSeconds |Average |SourceAddress, SourceName, SourceResourceId, SourceType, Protocol, DestinationAddress, DestinationName, DestinationResourceId, DestinationType, DestinationPort, TestGroupName, TestConfigurationName, SourceIP, DestinationIP, SourceSubnet, DestinationSubnet |Yes|
|Test Result<p><p>Connection monitor test result |`TestResult` |Count |Average |SourceAddress, SourceName, SourceResourceId, SourceType, Protocol, DestinationAddress, DestinationName, DestinationResourceId, DestinationType, DestinationPort, TestGroupName, TestConfigurationName, TestResultCriterion, SourceIP, DestinationIP, SourceSubnet, DestinationSubnet |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->