---
title: Example log table queries for AppDependencies
description:  Example queries for AppDependencies log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AppDependencies table


### Failing dependencies  


Which 5 dependencies failed the most today?  

```query
AppDependencies
| where Success == false
| summarize totalCount=sum(ItemCount) by DependencyType
| top 5 by totalCount desc
```

