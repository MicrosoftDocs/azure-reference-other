---
title: Example log table queries for EGNSuccessfulHttpDataPlaneOperations
description:  Example queries for EGNSuccessfulHttpDataPlaneOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/02/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EGNSuccessfulHttpDataPlaneOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### TLS 1.3 Lower query  


Clients using TLS of version lower than 1.3.  

```query
EGNSuccessfulHttpDataPlaneOperations
| where TLSVersion != "1.3"
| summarize count() by CallerIpAddress
```

