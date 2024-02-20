---
title: Example log table queries for MNFSystemStateMessageUpdates
description:  Example queries for MNFSystemStateMessageUpdates log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MNFSystemStateMessageUpdates table


### Find all errors from Syslog  


Syslog from device will be reported with message severity codes. This query filters all error messages from the Syslog.  

```query
MNFSystemStateMessageUpdates
| where Properties has "error"
| project EventName, EventCategory, DeviceId, TimeGenerated, Properties
| sort by TimeGenerated desc
| limit 100
```

