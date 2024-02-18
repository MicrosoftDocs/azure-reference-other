---
title: Example log table queries for ADTEventRoutesOperation
description:  Example queries for ADTEventRoutesOperation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADTEventRoutesOperation table


### EventRoutes API Usage  


Count of EventRoute APIs by type (read, write and delete).  

```query
ADTEventRoutesOperation
| summarize count() by OperationName
| render piechart
```

