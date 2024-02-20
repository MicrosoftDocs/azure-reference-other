---
title: Example log table queries for ConfigurationChange
description:  Example queries for ConfigurationChange log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ConfigurationChange table


### Stopped Windows services   


Find all windows services that stopped in the last 30 minutes.  

```query
// To create an alert for this query, click '+ New alert rule'
ConfigurationChange  // (relies on the Change Tracking solution): 
| where ConfigChangeType == "WindowsServices" and SvcChangeType == "State"
| where SvcPreviousState == "Running" and SvcState == "Stopped"
| where SvcStartupType == "Auto" and TimeGenerated > ago(30m)
```



### Software changes  


Lists software changes sorted by time (newest first).  

```query
ConfigurationChange
| where ConfigChangeType == "Software"
| sort by TimeGenerated desc
```



### Service changes  


Lists service changes sorted by time (newest first).  

```query
ConfigurationChange
| where ConfigChangeType == "Services"
| sort by TimeGenerated desc
```



### Software change type per computer  


Count software changes by computer.  

```query
ConfigurationChange 
| where ConfigChangeType == "Software"
| summarize AggregatedValue = count() by Computer
```



### Stopped services  


Lists stopped service changes sorted by time.  

```query
ConfigurationChange 
| where ConfigChangeType == "WindowsServices" and SvcState == "Stopped" 
| sort by TimeGenerated desc
```



### Software change count per category  


Count software changes by change category.  

```query
ConfigurationChange
| where ConfigChangeType == "Software"
| summarize AggregatedValue = count() by ChangeCategory
```



### Removed software changes  


Shows change records for removed software.  

```query
ConfigurationChange
| where ConfigChangeType == "Software" and ChangeCategory == "Removed"
| order by TimeGenerated desc
```

