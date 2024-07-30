---
title: Example log table queries for FailedIngestion
description:  Example queries for FailedIngestion log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the FailedIngestion table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Failed ingestions by errors  


How many ingestion failures accrued (by ErrorCode).  

```query
FailedIngestion 
| summarize count() by ErrorCode
```



### Failed ingestions timechart  


How many ingestion failures accrued (timechart).  

```query
FailedIngestion 
| summarize count() by bin(TimeGenerated, 5m) 
| render timechart 
```



### Failed Ingestions  


How many ingestion failures accrued (by cluster, database, table, ErrorCode, status).  

```query
FailedIngestion 
| parse _ResourceId with * "providers/microsoft.kusto/clusters/" cluster_name // Get the cluster name from the ResourceId string
| summarize count() by bin(TimeGenerated, 1h), cluster_name, Database, Table, ErrorCode, FailureStatus
```

