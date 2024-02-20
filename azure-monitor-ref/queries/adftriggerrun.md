---
title: Example log table queries for ADFTriggerRun
description:  Example queries for ADFTriggerRun log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADFTriggerRun table


### TriggerRuns Availability  


Gives the availability of the Trigger Runs.  

```query
// To create an alert for this query, click '+ New alert rule'
ADFTriggerRun
| where Status != 'Running' and Status != 'Waiting' and Status != 'WaitingOnDependency'
| where TriggerFailureType != 'UserError'
| summarize availability = 100.00 - (100.00*countif(Status != 'Succeeded') / count())  by bin(TimeGenerated, 1h)), _ResourceId
| order by TimeGenerated asc
| render timechart
```



### Trigger runs latest Status  


Returns latest Status of Trigger runs.  

```query
ADFTriggerRun
| summarize argmax(TimeGenerated, * ) by TriggerId, Status, _ResourceId
```

