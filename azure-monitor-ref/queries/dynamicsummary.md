---
title: Example log table queries for DynamicSummary
description:  Example queries for DynamicSummary log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DynamicSummary table


### Summary for hunting session  


Gets a list of dynamic summaries for a specific hunting session.  

```query
DynamicSummary
| where RelationName == "Hunt Session"
| where RelationId == "5b5a146c-eba8-46af-96f8-e31b50d15a3z"
| take 100

```

