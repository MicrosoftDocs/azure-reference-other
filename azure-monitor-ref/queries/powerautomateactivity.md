---
title: Example log table queries for PowerAutomateActivity
description:  Example queries for PowerAutomateActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the PowerAutomateActivity table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Power Automate events filtered by activity type  


Display events from more than one day ago, filtered CreateFlow activity type and summarized by user ID and flow details.  

```query
PowerAutomateActivity
| where EventOriginalType == "CreateFlow"
| summarize count() by ActorName, FlowDetailsUrl
```

