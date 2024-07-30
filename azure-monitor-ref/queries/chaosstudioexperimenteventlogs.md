---
title: Example log table queries for ChaosStudioExperimentEventLogs
description:  Example queries for ChaosStudioExperimentEventLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ChaosStudioExperimentEventLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Failed experiment runs  


List failed experiment runs.  

```query
ChaosStudioExperimentEventLogs
| where Status == 'Failed' and SpanType == 'Experiment'
| sort by TimeGenerated desc
```



### Experiment events on last experiment run  


List experiment events on the last experiment run.  

```query
ChaosStudioExperimentEventLogs
| lookup kind=inner (
    ChaosStudioExperimentEventLogs
    | top 1 by TimeGenerated desc
    | project CorrelationId
) on CorrelationId
| order by TimeGenerated asc
```

