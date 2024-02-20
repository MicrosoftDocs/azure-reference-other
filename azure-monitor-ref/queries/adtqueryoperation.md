---
title: Example log table queries for ADTQueryOperation
description:  Example queries for ADTQueryOperation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADTQueryOperation table


### Query Error Summary  


List of all Query call errors.  

```query
ADTQueryOperation
| where ResultType != 'Success'
```

