---
title: Example log table queries for LAQueryLogs
description:  Example queries for LAQueryLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the LAQueryLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Most Requested ResourceIds  


Most queried resources over the last 24 hours.  

```query
LAQueryLogs
| extend reqContext = parse_json(RequestContext)
| extend datasources = array_concat(reqContext["resources"], reqContext["workspaces"], reqContext["applications"])
| mv-expand datasources
| summarize reqCount = count() by tostring(datasources)
| order by reqCount desc
```



### Unauthorized Users  


Get a list of unauthorized users with their request count in last 24 hours.  

```query
LAQueryLogs
| where ResponseCode == "403"
| summarize reqCount = count() by AADObjectId
| order by reqCount desc
```



### Throttled Users  


Get a list of throttled users with their request count in last 24 hours.  

```query
LAQueryLogs
| where ResponseCode == "429"
| summarize reqCount = count() by AADObjectId
| order by reqCount desc
```



### Request Count by ResponseCode  


Request count by response code within 1 min buckets in last 1 hour.  

```query
LAQueryLogs
| where TimeGenerated > ago(1h)
| summarize count() by tostring(ResponseCode), bin(TimeGenerated, 1m)
| render columnchart with (kind=stacked)
```



### Top 10 resource intensive queries  


Get top 10 resource intesive queries (based on CPU consumption) in last 24 hours.  

```query
LAQueryLogs
| top 10 by StatsCPUTimeMs desc nulls last 
```



### Top 10 longest time range queries  


Get top 10 queries that scanned the longest time range in last 24 hours.  

```query
LAQueryLogs
| extend DataProcessedTimeRange = format_timespan(StatsDataProcessedEnd - StatsDataProcessedStart, 'dd.hh:mm:ss:FF')
| top 10 by DataProcessedTimeRange desc nulls last 
```

