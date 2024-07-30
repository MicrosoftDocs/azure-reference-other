---
title: Example log table queries for StorageCacheOperationEvents
description:  Example queries for StorageCacheOperationEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the StorageCacheOperationEvents table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Failed operation  


Retrieves a list of operation that returned a failed response code.  

```query
StorageCacheOperationEvents
| where ResponseCode < 200 or ResponseCode >= 300
| sort by TimeGenerated desc
| take 100
```



### Failed priming job  


Retrieves a list of failed priming jobs.  

```query
StorageCacheOperationEvents
| where OperationName contains "Priming"
| where ResultType == "Failed"
| project  TimeGenerated, OperationName, PrimingJobName, ResultDescription, _ResourceId, CorrelationId, Location
| sort by TimeGenerated desc
| take 100
```



### Completed long-running asynchronous operations  


Retrieves a list of long-running operations that have completed.  

```query
StorageCacheOperationEvents
| where ResponseCode == 201 or ResponseCode == 202
| where ResultType == "Succeeded" 
| sort by TimeGenerated desc
| take 100
```

