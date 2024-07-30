---
title: Example log table queries for ASRReplicatedItems
description:  Example queries for ASRReplicatedItems log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ASRReplicatedItems table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


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

