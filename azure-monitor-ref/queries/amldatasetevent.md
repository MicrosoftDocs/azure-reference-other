---
title: Example log table queries for AmlDataSetEvent
description:  Example queries for AmlDataSetEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlDataSetEvent table


### Count datasets reads  


Count datasets reads grouped by users and datasets.  

```query
AmlDataSetEvent
| where split(OperationName, "/")[-1]=="READ" and AmlDatasetId !=""
| extend  Identity=(parse_json(Identity))
| project AmlDatasetId, UserName=Identity.UserName
| summarize  Count=count() by AmlDatasetId, UserName=tostring(UserName)
```

