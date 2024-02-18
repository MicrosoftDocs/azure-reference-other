---
title: Example log table queries for ContainerInventory
description:  Example queries for ContainerInventory log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ContainerInventory table


### Container Lifecycle Information  


List all of a container's lifecycle information.  

```query
// Container Lifecycle Information 
// List all of a container's lifecycle information. 
ContainerInventory
| project Computer, Name, Image, ImageTag, ContainerState, CreatedTime, StartedTime, FinishedTime
| top 200 by FinishedTime desc
```

