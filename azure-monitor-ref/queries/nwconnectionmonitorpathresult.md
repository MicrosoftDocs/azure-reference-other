---
title: Example log table queries for NWConnectionMonitorPathResult
description:  Example queries for NWConnectionMonitorPathResult log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the NWConnectionMonitorPathResult table


### Path diagnostics  


Gets path or all hops along with identified issues between given source and destination of a resource.  

```query
// For specific results, insert values in the let statements and uncomment the where filters within the query
// let connectionMonitorResourceId = "<Connection Monitor Resource Id>";
// let sourceName = "<Source Name>";
// let destinationName = "<Destination Name>";
// let testGroupName = "<Test Group Name>";
// let testConfigurationName = "<Test Configuration Name>";
NWConnectionMonitorPathResult 
| where TimeGenerated > ago(24h) 
// | where ConnectionMonitorResourceId has connectionMonitorResourceId
// | where SourceName has sourceName
// | where DestinationName has destinationName
// | where TestGroupName has testGroupName
// | where TestConfigurationName has testConfigurationName
| project TimeGenerated, ConnectionMonitorResourceId, PathTestResult, SourceName, SourceAddress, DestinationName, DestinationAddress, Hops
| order by TimeGenerated desc;
```

