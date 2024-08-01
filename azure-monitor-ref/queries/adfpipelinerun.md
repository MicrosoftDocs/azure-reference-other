---
title: Example log table queries for ADFPipelineRun
description:  Example queries for ADFPipelineRun log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADFPipelineRun table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### PipelineRuns Availability  


Gives the availability of the Pipeline Runs.  

```query
// To create an alert for this query, click '+ New alert rule'
ADFPipelineRun
| where Status != 'InProgress' and Status != 'Queued'
| where FailureType != 'UserError'
| summarize availability = 100.00 - (100.00*countif(Status != 'Succeeded') / count())  by bin(TimeGenerated, 1h)), _ResourceId
| order by TimeGenerated asc
| render timechart
```



### Pipeline runs latest Status  


Returns latest Status of pipeline runs.  

```query
ADFPipelineRun
| summarize argmax(TimeGenerated, * ) by RunId, Status, _ResourceId
```

