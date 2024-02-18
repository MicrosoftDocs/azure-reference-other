---
title: Example log table queries for AmlRegistryWriteEventsLog
description:  Example queries for AmlRegistryWriteEventsLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlRegistryWriteEventsLog table


### All WRITE events  


Retrieves a list of events of WRITE.  

```query
AmlRegistryWriteEventsLog
| project
	TimeGenerated,
	RegistryResourceId,
	OperationType,
	UserName,
	AssetName,
	AssetVersion
| top 100 by TimeGenerated
```

