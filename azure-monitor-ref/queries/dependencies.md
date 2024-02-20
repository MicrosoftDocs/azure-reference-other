---
title: Example log table queries for dependencies
description:  Example queries for dependencies log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the dependencies table


### Failing dependencies  


Which 5 dependencies failed the most today?  

```query
dependencies
| where success == false
| summarize totalCount=sum(itemCount) by type
| top 5 by totalCount desc
```

