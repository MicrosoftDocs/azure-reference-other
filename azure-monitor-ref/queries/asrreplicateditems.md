---
title: Example log table queries for ASRReplicatedItems
description:  Example queries for ASRReplicatedItems log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ASRReplicatedItems table


### Get replication health status history  


Get replication health status history for a virtual machine.  

```query
let replicatedItemFriendlyName = "<insert your replicated item friendly name>";
ASRReplicatedItems
//| where TimeGenerated >= ago(30d) // uncomment this line to view last 30 days
//| where _ResourceId == resourceId // uncomment this line and enter resource ID
| where ReplicatedItemFriendlyName == replicatedItemFriendlyName
| project Day=startofday(TimeGenerated), TimeGenerated, ReplicatedItemId, ReplicatedItemFriendlyName, ReplicationStatus
| summarize arg_max(TimeGenerated,*) by Day
```

