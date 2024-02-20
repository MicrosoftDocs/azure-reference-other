---
title: Example log table queries for StorageCacheWarningEvents
description:  Example queries for StorageCacheWarningEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the StorageCacheWarningEvents table


### Active warning events  


Retrieves a list of warning events that have not cleared.  

```query
StorageCacheWarningEvents
| where State == "Active"
| project TimeGenerated, CorrelationId, Description, _ResourceId, State
| join kind=leftanti (StorageCacheWarningEvents
    | where State == "Cleared"
        | project TimeGenerated, CorrelationId, Description, _ResourceId, State)
    on CorrelationId
| project TimeGenerated, CorrelationId, Description, _ResourceId, State
| take 100

```

