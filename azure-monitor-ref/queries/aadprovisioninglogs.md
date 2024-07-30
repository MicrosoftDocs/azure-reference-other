---
title: Example log table queries for AADProvisioningLogs
description:  Example queries for AADProvisioningLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADProvisioningLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Provisioning actions for the last week  


Shows the number of users and groups created, updated, disabled, and deleted in the past 7 days.  

```query
AADProvisioningLogs
| where TimeGenerated > ago(7d)
| where ResultType == "Success"
| parse SourceIdentity with * "\"identityType\":\"" Type "\"" *
| extend Type = tolower(Type)
| summarize count() by Type, Action
| order by Type, Action
```



### Provisioning errors  


Shows the count per error code and when were they last seen.  

```query
AADProvisioningLogs
| where ResultType == "Failure"
| summarize Occurrences=count(), LastSeen=max(TimeGenerated) by ResultSignature
| order by LastSeen
```



### Provisioned objects by day  


Summarizes for each day the number of created objects per day.  

```query
AADProvisioningLogs
| where TimeGenerated > ago(7d)
| where ResultType == "Success"
| where Action == "Create"
| parse SourceIdentity with * "\"identityType\":\"" Type "\"" *
| extend Type = tolower(Type)
| summarize count() by Type, bin(TimeGenerated, 1d)
| render columnchart
```

