---
title: Example log table queries for AADServicePrincipalSignInLogs
description:  Example queries for AADServicePrincipalSignInLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADServicePrincipalSignInLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Most active service principals  


Gets list of top 100 most active service principals for the last day.  

```query
AADServicePrincipalSignInLogs
| where TimeGenerated > ago(1d)
| summarize CountPerServicePrincipal = count() by ServicePrincipalId
| order by CountPerServicePrincipal desc
| take 100
```



### Inactive service principals  


Service principals that had no sign-ins for the last 30d.  

```query
AADServicePrincipalSignInLogs
| where TimeGenerated > ago(90d)
| where ResultType == 0
| summarize LastSignIn = max(TimeGenerated) by ServicePrincipalId
| where LastSignIn < ago(30d)
```

