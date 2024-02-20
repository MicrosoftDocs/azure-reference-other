---
title: Example log table queries for AutoscaleScaleActionsLog
description:  Example queries for AutoscaleScaleActionsLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AutoscaleScaleActionsLog table


### Display top Autoscale 50 logs  


Show the latest Azure Autoscale logs in the last 24 hours.  

```query
AutoscaleScaleActionsLog 
| where TimeGenerated > ago(24h) 
| limit 50
```



### Autoscale operation status  


Lists latest Autoscale operations, scale direction, instance count and it's status.  

```query
AutoscaleScaleActionsLog
| project TimeGenerated, ResourceId, CurrentInstanceCount, NewInstanceCount, ScaleDirection, ResultType
| sort by TimeGenerated desc 
```



### Autoscale failed operations  


List all reports of failed operations, over the last day.  

```query
// To create an alert for this query, click '+ New alert rule'
AutoscaleScaleActionsLog 
| where TimeGenerated > ago(24h)  
| where ResultType == "Failed"
```

