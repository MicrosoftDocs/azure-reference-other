---
title: Example log table queries for AppExceptions
description:  Example queries for AppExceptions log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppExceptions table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Top 3 browser exceptions  


What were the highest reported exceptions today?  

```query
AppExceptions
| where notempty(ClientBrowser) and ClientType == 'Browser'
| summarize total_exceptions = sum(ItemCount) by ProblemId
| top 3 by total_exceptions desc
```

