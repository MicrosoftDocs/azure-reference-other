---
title: Example log table queries for AutoscaleEvaluationsLog
description:  Example queries for AutoscaleEvaluationsLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AutoscaleEvaluationsLog table


### Review Autoscale evaluations  


Counts Autoscale evaluations in the last hour.  

```query
AutoscaleEvaluationsLog
| where TimeGenerated > ago(1h)
| summarize count() by ResourceId, Profile, OperationName, EvaluationResult
```

