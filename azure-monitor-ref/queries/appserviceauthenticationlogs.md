---
title: Example log table queries for AppServiceAuthenticationLogs
description:  Example queries for AppServiceAuthenticationLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppServiceAuthenticationLogs table


### Most recent errors from App Service Authentication  


Lists up to 100 most recent errors from App Service Authentication in selected time range.  

```query
AppServiceAuthenticationLogs
| where TaskName == "MiddlewareError"
| sort by TimeGenerated desc
| take 100
```



### Most recent warnings from App Service Authentication  


Lists up to 100 most recent warnings from App Service Authentication in selected time range.  

```query
AppServiceAuthenticationLogs
| where TaskName == "MiddlewareWarning"
| sort by TimeGenerated desc
| take 100
```



### Top 100 most frequent errors and warnings from App Service Authentication  


Count of top 100 most frequent error and warning messages from App Service Authentication in selected time range, sorted by type (errors shown first), then descending count.  

```query
AppServiceAuthenticationLogs
| where TaskName == "MiddlewareWarning" or TaskName == "MiddlewareError"
| summarize count() by Message, TaskName
| order by TaskName asc, count_
| take 100
```

