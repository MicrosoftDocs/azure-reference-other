---
title: Example log table queries for NWConnectionMonitorTestResult
description:  Example queries for NWConnectionMonitorTestResult log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the NWConnectionMonitorTestResult table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Failed tests  


Gets failed distinct source, destination, test group and test configuration for each resource.  

```query
NWConnectionMonitorTestResult 
| where TimeGenerated > ago(24h) 
| where TestResult == "Fail"
| distinct _ResourceId, SourceName, DestinationName, TestGroupName, TestConfigurationName
```



### Tests performance  


Gets loss percentage and average latency between given source and destination of a resource.  

```query
// For specific results, insert values in the let statements and uncomment the where filters within the query
// let connectionMonitorResourceId = "<Connection Monitor Resource Id>";
// let sourceName = "<Source Name>";
// let destinationName = "<Destination Name>";
// let testGroupName = "<Test Group Name>";
// let testConfigurationName = "<Test Configuration Name>";
NWConnectionMonitorTestResult 
| where TimeGenerated > ago(24h) 
// | where ConnectionMonitorResourceId has connectionMonitorResourceId
// | where SourceName has sourceName
// | where DestinationName has destinationName
// | where TestGroupName has testGroupName
// | where TestConfigurationName has testConfigurationName
| extend LossPercent = ChecksFailed * 100 / ChecksTotal
| project TimeGenerated, ConnectionMonitorResourceId, TestResult, AvgRoundTripTimeMs, LossPercent, SourceName, SourceAddress, DestinationName, DestinationAddress
| order by TimeGenerated desc;
```

