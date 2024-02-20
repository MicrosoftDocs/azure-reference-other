---
title: Example log table queries for AppPlatformLogsforSpring
description:  Example queries for AppPlatformLogsforSpring log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppPlatformLogsforSpring table


### Show the application logs which contain the "error" or "exception" terms  


Show the application logs which contain the "error" or "exception" terms in the last hour.  

```query
// To create an alert for this query, click '+ New alert rule'
AppPlatformLogsforSpring
| where TimeGenerated > ago(1h)
| where Log contains "error" or Log contains "exception"
| project TimeGenerated , ServiceName , AppName , InstanceName , Log , _ResourceId 
```



### Show the error and exception number of each application  


Show a pie chart of the number of the logs containing the "error" or "exception" terms in the last 24 hours, per application.  

```query
// To create an alert for this query, click '+ New alert rule'
AppPlatformLogsforSpring 
| where TimeGenerated > ago(24h)
| where Log contains "error" or Log contains "exception"
| extend FullAppName = strcat(ServiceName, "/", AppName)
| summarize count_per_app = count() by FullAppName, ServiceName, AppName, _ResourceId
| sort by count_per_app desc 
| render piechart
```

