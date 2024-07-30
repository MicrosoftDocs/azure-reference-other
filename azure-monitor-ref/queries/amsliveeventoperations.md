---
title: Example log table queries for AMSLiveEventOperations
description:  Example queries for AMSLiveEventOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AMSLiveEventOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Live event ingest discontinuity operation count  


Summarizes the count of ingest discontinuities by different live events.  

```query
AMSLiveEventOperations
| where OperationName == "LIVEEVENTS/INGESTDISCONTINUITY"
| summarize Count = count() by tostring(Properties.liveEventName)
```



### Live event error operations  


Lists the live event error operations.  

```query
AMSLiveEventOperations
| where Level == "Error"
| project _ResourceId, OperationName
| limit 100
```

