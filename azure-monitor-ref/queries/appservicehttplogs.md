---
title: Example log table queries for AppServiceHTTPLogs
description:  Example queries for AppServiceHTTPLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppServiceHTTPLogs table


### App Service Health  


Time series of App Service Health (over 5 minute intervals).  

```query
AppServiceHTTPLogs 
| summarize (count() - countif(ScStatus >= 500)) * 100.0 / count() by bin(TimeGenerated, 5m), _ResourceId
| render timechart 
```



### Failure Categorization  


Categorize all requests which resulted in 5xx.  

```query
AppServiceHTTPLogs 
//| where ResourceId = "MyResourceId" // Uncomment to get results for a specific resource Id when querying over a group of Apps
| where ScStatus >= 500
| reduce by strcat(CsMethod, ':\\', CsUriStem)
```



### Response times of requests  


Avg & 90, 95 and 99 percentile response times (in milliseconds) per App Service.  

```query
AppServiceHTTPLogs 
| summarize avg(TimeTaken), percentiles(TimeTaken, 90, 95, 99) by _ResourceId
```



### Top 5 Clients  


Top 5 clients which are generating traffic.  

```query
AppServiceHTTPLogs
| top-nested of _ResourceId by dummy=max(0), // Display results for each resource (App)
  top-nested 5 of UserAgent by count()
| project-away dummy // Remove dummy line from the result set
```



### Top 5 Machines  


Top 5 machines which are generating traffic.  

```query
AppServiceHTTPLogs
| top-nested of _ResourceId by dummy=max(0), // Display results for each resource (App)
  top-nested 5 of CIp by count()
| project-away dummy // Remove dummy line from the result set
```

