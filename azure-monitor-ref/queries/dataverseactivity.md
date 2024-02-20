---
title: Example log table queries for DataverseActivity
description:  Example queries for DataverseActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DataverseActivity table


### Dataverse events filtered by operation type  


Display events filtered by Create record operations and summarized by associated table name.  

```query
DataverseActivity
| where Message == "Create"
| summarize count() by EntityName
```

