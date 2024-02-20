---
title: Example log table queries for AgriFoodJobProcessedLogs
description:  Example queries for AgriFoodJobProcessedLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AgriFoodJobProcessedLogs table


### Job execution statistics for a farmer  


Retrieves the status of job processing for a farmer.  

```query
AgriFoodJobProcessedLogs
| summarize Count = count() by FarmerId, ResultType, OperationName

```

