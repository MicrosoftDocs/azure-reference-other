---
title: Example log table queries for LogicAppWorkflowRuntime
description:  Example queries for LogicAppWorkflowRuntime log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the LogicAppWorkflowRuntime table


### Count of failed workflow operations from Logic App Workflow Runtime  


Count of failed workflow operations from Logic App Workflow Runtime in selected time range for each workflow.  

```query
LogicAppWorkflowRuntime
| where Status == "Failed"
| summarize count() by WorkflowName
```

