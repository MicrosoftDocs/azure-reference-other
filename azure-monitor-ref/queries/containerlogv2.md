---
title: Example log table queries for ContainerLogV2
description:  Example queries for ContainerLogV2 log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ContainerLogV2 table


### Find In ContainerLogV2  


Find in ContainerLogV2 to search for a specific value in the ContainerLogV2 table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
ContainerLogV2
| where * contains tostring(SearchValue)
| take 1000
```

