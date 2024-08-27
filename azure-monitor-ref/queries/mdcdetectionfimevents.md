---
title: Example log table queries for MDCDetectionFimEvents
description:  Example queries for MDCDetectionFimEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/26/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MDCDetectionFimEvents table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### All FIM events for directories  


Get all FIM events against directories of the host.  

```query
MDCDetectionFimEvents
| where IsDir == "True"
| order by TimeGenerated
| limit 100
```

