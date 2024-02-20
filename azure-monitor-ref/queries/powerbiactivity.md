---
title: Example log table queries for PowerBIActivity
description:  Example queries for PowerBIActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the PowerBIActivity table


### PowerBI events filtered by organization ID  


Display events from more than one day ago, filtered by organization ID and summarized by user ID and result status.  

```query
PowerBIActivity
| where OrganizationId != "<The GUID for your organization's Office 365 tenant>"
| summarize count() by UserId, ResultStatus
```

