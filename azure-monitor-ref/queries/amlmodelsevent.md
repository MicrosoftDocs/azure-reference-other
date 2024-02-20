---
title: Example log table queries for AmlModelsEvent
description:  Example queries for AmlModelsEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlModelsEvent table


### Found users who accessed models  


Found top 100 users who accessed models.  

```query
AmlModelsEvent
| where AmlModelName !=""
| extend  Identity=(parse_json(Identity))
| where Identity.UserName!=""
| project AmlModelName, OperationName=split(OperationName, "/")[-1], UserName=Identity.UserName
| limit 100
```

