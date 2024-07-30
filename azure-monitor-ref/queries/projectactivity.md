---
title: Example log table queries for ProjectActivity
description:  Example queries for ProjectActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ProjectActivity table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### MS Project events filtered by organization ID  


Display events from more than one day ago, filtered by organization ID and summarized by user ID and result status.  

```query
ProjectActivity
| where OrganizationId != "5b5a146c-eba8-46af-96f8-e31b50d15a3f"
| summarize count() by UserId, ResultStatus

```

