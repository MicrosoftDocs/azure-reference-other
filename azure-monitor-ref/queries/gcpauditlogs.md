---
title: Example log table queries for GCPAuditLogs
description:  Example queries for GCPAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the GCPAuditLogs table


### PubSub subscription logs with severity info  


List of pubSub subscription logs with severity info.  

```query
GCPAuditLogs
| where  GCPResourceType == 'pubsub_subscription'
| where  severity == 'INFO'
| limit 100
```

