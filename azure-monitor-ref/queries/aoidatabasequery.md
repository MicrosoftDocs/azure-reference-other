---
title: Example log table queries for AOIDatabaseQuery
description:  Example queries for AOIDatabaseQuery log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AOIDatabaseQuery table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Queries executed by a user on dataproduct  


List all the queries run on a dataproduct by a particular user.  

```query
AOIDatabaseQuery
| where DatabaseName has_cs "edrdp" and User has_cs "username@domain.com"
| take 100
```

