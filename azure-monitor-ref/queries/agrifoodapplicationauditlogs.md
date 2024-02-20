---
title: Example log table queries for AgriFoodApplicationAuditLogs
description:  Example queries for AgriFoodApplicationAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AgriFoodApplicationAuditLogs table


### Failed authorization  


Identifies a list of users who failed to access your resource and the reason for this failure.  

```query
AgriFoodApplicationAuditLogs
| where OperationName startswith "Data Plane Authentication"
| where ResultType == "Failure"
| take 100

```

