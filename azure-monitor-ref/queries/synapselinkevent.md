---
title: Example log table queries for SynapseLinkEvent
description:  Example queries for SynapseLinkEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SynapseLinkEvent table


### Synapse Link table fail events  


Display sample failed Synapse Link table events.  

```query
SynapseLinkEvent
| where OperationName == "TableFail"
| limit 100
```

