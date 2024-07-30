---
title: Example log table queries for AmlRegistryWriteEventsLog
description:  Example queries for AmlRegistryWriteEventsLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AmlRegistryWriteEventsLog table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


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

