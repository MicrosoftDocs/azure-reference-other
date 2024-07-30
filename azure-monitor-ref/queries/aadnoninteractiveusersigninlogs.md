---
title: Example log table queries for AADNonInteractiveUserSignInLogs
description:  Example queries for AADNonInteractiveUserSignInLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADNonInteractiveUserSignInLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Users with multiple cities  


Get list of users that signed in from multiple cities for the last day.  

```query
AADNonInteractiveUserSignInLogs
| where TimeGenerated > ago(1d)
| extend City = parse_json(LocationDetails).city
| summarize CountPerCity = dcount(tostring(City)) by UserId
| where CountPerCity > 1
| order by CountPerCity desc
```



### Most active ip addresses  


Get list of top 100 most active IP addresses for the last day.  

```query
AADNonInteractiveUserSignInLogs
| where TimeGenerated > ago(1d)
| summarize CountPerIPAddress = count() by IPAddress
| order by CountPerIPAddress desc
| take 100
```

