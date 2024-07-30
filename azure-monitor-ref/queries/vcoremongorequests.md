---
title: Example log table queries for VCoreMongoRequests
description:  Example queries for VCoreMongoRequests log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the VCoreMongoRequests table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Mongo vCore requests P99 duration by operation  


Mongo vCore requests P99 runtime duration by operation name.  

```query
VCoreMongoRequests
// Time range filter:  | where TimeGenerated between (StartTime .. EndTime)
// Resource id filter: | where _ResourceId == "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/my-resource-group-name/providers/microsoft.documentdb/mongoclusters/my-cluster-name"
| summarize percentile(DurationMs, 99) by bin(TimeGenerated, 1h), OperationName

```



### Mongo vCore requests binned by duration  


Count of Mongo vCore requests binned by total runtime duration.  

```query
VCoreMongoRequests
// Time range filter:  | where TimeGenerated between (StartTime .. EndTime)
// Resource id filter: | where _ResourceId == "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/my-resource-group-name/providers/microsoft.documentdb/mongoclusters/my-cluster-name"
| project TimeGenerated, DurationBin=tostring(bin(DurationMs, 5))
| summarize count() by bin(TimeGenerated, 1m), tostring(DurationBin)

```



### Failed Mongo vCore requests  


Count of failed Mongo vCore requests by error code.  

```query
VCoreMongoRequests
// Time range filter:  | where TimeGenerated between (StartTime .. EndTime)
// Resource id filter: | where _ResourceId == "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/my-resource-group-name/providers/microsoft.documentdb/mongoclusters/my-cluster-name"
| where ErrorCode != 0
| summarize count() by bin(TimeGenerated, 5m), ErrorCode=tostring(ErrorCode)

```



### Mongo vCore requests by user agent  


Count of Mongo vCore requests by user agent.  

```query
VCoreMongoRequests
// Time range filter:  | where TimeGenerated between (StartTime .. EndTime)
// Resource id filter: | where _ResourceId == "/subscriptions/00000000-0000-0000-0000-000000000000/resourcegroups/my-resource-group-name/providers/microsoft.documentdb/mongoclusters/my-cluster-name"
| summarize count() by bin(TimeGenerated, 1h), UserAgent

```

