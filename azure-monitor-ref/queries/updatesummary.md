---
title: Example log table queries for UpdateSummary
description:  Example queries for UpdateSummary log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the UpdateSummary table


### Summary of updates available across machines  


Count of updates available under various categories for each machine.  

```query
// To create an alert for this query, click '+ New alert rule'
UpdateSummary 
| where TimeGenerated>ago(14h) 
| summarize by Computer, CriticalUpdatesMissing, SecurityUpdatesMissing, OtherUpdatesMissing, TotalUpdatesMissing, ResourceId
```



### Missing update specific product  


WSUS computer membership.  

```query
// To create an alert for this query, click '+ New alert rule'
UpdateSummary
| summarize AggregatedValue = count() by WSUSServer, Computer, _ResourceId
```



### Automatic update configuration  


Automatic update configuration.  

```query
// To create an alert for this query, click '+ New alert rule'
UpdateSummary
| summarize AggregatedValue = count() by WindowsUpdateSetting, Computer, _ResourceId
```



### Automatic update configuration is disabled  


Computers with automatic update disabled.  

```query
// To create an alert for this query, click '+ New alert rule'
UpdateSummary
| where WindowsUpdateSetting == "Manual" 
| sort by TimeGenerated desc
```

