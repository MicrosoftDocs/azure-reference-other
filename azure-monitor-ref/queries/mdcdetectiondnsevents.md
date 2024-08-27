---
title: Example log table queries for MDCDetectionDNSEvents
description:  Example queries for MDCDetectionDNSEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/26/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MDCDetectionDNSEvents table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### All DNS events where the domain queried was 'www.google.com' ordered by time  


Get all DNS events where the domain queried was 'www.google.com' ordered by time.  

```query
MDCDetectionDNSEvents
| where Domain == "www.google.com"
| order by TimeGenerated
| limit 100
```

