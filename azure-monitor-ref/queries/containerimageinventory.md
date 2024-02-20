---
title: Example log table queries for ContainerImageInventory
description:  Example queries for ContainerImageInventory log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ContainerImageInventory table


### Image inventory  


Lists all the container image with their status.  

```query
ContainerImageInventory
| summarize AggregatedValue = count() by Image, ImageTag, Running, _ResourceId
```



### Find In ContainerImageInventory  


Find in ContainerImageInventory to search for a specific value in the ContainerImageInventory table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
ContainerImageInventory
| where * contains tostring(SearchValue)
| take 1000
```

