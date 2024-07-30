---
title: Example log table queries for MNFSystemStateMessageUpdates
description:  Example queries for MNFSystemStateMessageUpdates log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MNFSystemStateMessageUpdates table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Find all errors from Syslog  


Syslog from device will be reported with message severity codes. This query filters all error messages from the Syslog.  

```query
MNFSystemStateMessageUpdates
| where Properties has "error"
| project EventName, EventCategory, DeviceId, TimeGenerated, Properties
| sort by TimeGenerated desc
| limit 100
```

