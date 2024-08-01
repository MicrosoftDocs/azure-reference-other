---
title: Example log table queries for WaaSUpdateStatus
description:  Example queries for WaaSUpdateStatus log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WaaSUpdateStatus table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Distribution of device Servicing Branch  


Pie chart of devices distribution by servicing branch.  

```query
WaaSUpdateStatus
| summarize arg_max(TimeGenerated, *) by ComputerID
| project ComputerID, OSServicingBranch
| summarize dcount(ComputerID) by OSServicingBranch
| render piechart
```



### Distribution of device OS Edition  


Counts devices by OS edition.  

```query
WaaSUpdateStatus
| summarize arg_max(TimeGenerated, *) by ComputerID
| project TimeGenerated, ComputerID, OSEdition
| summarize dcount(ComputerID) by OSEdition
```



### Feature Update Deferral Configurations  


Chart of device count by feature update deferral configurations.  

```query
WaaSUpdateStatus
| summarize arg_max(TimeGenerated, *) by ComputerID
| project TimeGenerated, ComputerID, FeatureDeferralDays
| summarize dcount(ComputerID) by FeatureDeferralDays
| sort by FeatureDeferralDays asc
| render columnchart
```



### Feature Update Pause Configurations  


Count devices by feature update pause configurations.  

```query
WaaSUpdateStatus
| summarize arg_max(TimeGenerated, *) by ComputerID
| project TimeGenerated, ComputerID, FeaturePauseState
| summarize dcount(ComputerID) by FeaturePauseState
```



### Quality Update Deferral Configurations  


Chart of device count by quality update deferral configurations.  

```query
WaaSUpdateStatus
| summarize arg_max(TimeGenerated, *) by ComputerID
| project TimeGenerated, ComputerID, QualityDeferralDays
| summarize dcount(ComputerID) by QualityDeferralDays
| sort by QualityDeferralDays asc
| render columnchart
```



### Quality Update Pause Configurations  


Count devices by quality update pause configurations.  

```query
WaaSUpdateStatus
| summarize arg_max(TimeGenerated, *) by ComputerID
| project TimeGenerated, ComputerID, QualityPauseState
| summarize dcount(ComputerID) by QualityPauseState
```

