---
title: Example log table queries for ADXTableUsageStatistics
description:  Example queries for ADXTableUsageStatistics log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADXTableUsageStatistics table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Table usage by number of queries  


Top 10 used tables by number of queries.  

```query
ADXTableUsageStatistics
//| parse _ResourceId with * "providers/microsoft.kusto/clusters/" cluster_name // Uncomment to get the cluster name from the ResourceId string
//| where cluster_name == '<Your cluster name filter>'
//| where DatabaseName == '<Your database name filter>'
| summarize Count=count() by TableName, DatabaseName
| top 10 by Count desc
| order by Count desc
```



### Table usage by application  


Top 10 used tables (highest number of queries) by application.  

```query
ADXTableUsageStatistics 
//| parse _ResourceId with * "providers/microsoft.kusto/clusters/" cluster_name // Uncomment to get the cluster name from the ResourceId string
//| where cluster_name == '<Your cluster name filter>'
//| where DatabaseName == '<Your database name filter>'
| summarize Count=count() by TableName, DatabaseName, ApplicationName
| top 10 by Count desc
| order by Count desc
```



### Table data scanned - top time windows  


Top 10 data scanned lookback time windows.  

```query
ADXTableUsageStatistics 
//| parse _ResourceId with * ""providers/microsoft.kusto/clusters/"" cluster_name // Uncomment to get the cluster name from the ResourceId string
//| where cluster_name == '<Your cluster name filter>'
//| where DatabaseName == '<Your database name filter>'
//| where TableName == '<Your table name filter>'
| extend TotalTime = (MaxCreatedOn - MinCreatedOn)
| top 10 by TotalTime desc
| order by TotalTime desc
| project TimeGenerated, TotalTime, TableName, DatabaseName, MinCreatedOn, MaxCreatedOn, ApplicationName
```



### Table data scanned - top tables  


Top 10 data scanned lookback time windows by table.  

```query
ADXTableUsageStatistics 
//| parse _ResourceId with * ""providers/microsoft.kusto/clusters/"" cluster_name // Uncomment to get the cluster name from the ResourceId string
//| where cluster_name == '<Your cluster name filter>'
//| where DatabaseName == '<Your database name filter>'
//| where TableName == '<Your table name filter>'
| extend TotalTime = (MaxCreatedOn - MinCreatedOn)
| summarize arg_max(TotalTime, *) by TableName
| order by TotalTime desc
| project TimeGenerated, TotalTime, TableName, DatabaseName, MinCreatedOn, MaxCreatedOn, ApplicationName
```

