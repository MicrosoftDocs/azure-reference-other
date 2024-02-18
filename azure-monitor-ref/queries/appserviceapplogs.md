---
title: Example log table queries for AppServiceAppLogs
description:  Example queries for AppServiceAppLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppServiceAppLogs table


### Count app logs by severity  


Bar chart of app log severities over time.  

```query
// To create an alert for this query, click '+ New alert rule'
AppServiceAppLogs 
| summarize count()  by CustomLevel, bin(TimeGenerated, 1h), _ResourceId
| render barchart 
```



### App logs for each App Service  


Breakdown of log levels for each App Service.  

```query
// To create an alert for this query, click '+ New alert rule'
AppServiceAppLogs 
| project CustomLevel, _ResourceId
| summarize count() by CustomLevel, _ResourceId
```

