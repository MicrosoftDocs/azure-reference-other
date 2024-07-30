---
title: Example log table queries for AGCAccessLogs
description:  Example queries for AGCAccessLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AGCAccessLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Client requests per hour  


Count of client requests hourly.  

```query
AGCAccessLogs
| summarize AggregatedValue = count() by bin(TimeGenerated, 1h), _ResourceId
| render timechart
```



### 5xx HTTP responses per hour  


Count of client requests that resulted in 5xx responses hourly.  

```query
AGCAccessLogs
| where HttpStatusCode > 499 and HttpStatusCode < 600
| summarize AggregatedValue = count() by bin(TimeGenerated, 1h), _ResourceId
| render timechart
```



### 4xx HTTP responses per hour  


Count of client requests that resulted in 4xx responses hourly.  

```query
AGCAccessLogs
| where HttpStatusCode > 399 and HttpStatusCode < 500
| summarize AggregatedValue = count() by bin(TimeGenerated, 1h), _ResourceId
| render timechart
```

