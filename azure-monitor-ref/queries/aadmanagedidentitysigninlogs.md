---
title: Example log table queries for AADManagedIdentitySignInLogs
description:  Example queries for AADManagedIdentitySignInLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADManagedIdentitySignInLogs table


### Most active managed identities  


Gets list of top 100 most active managed identities for the last day.  

```query
AADManagedIdentitySignInLogs
| where TimeGenerated > ago(1d)
| summarize CountPerManagedIdentity = count() by ServicePrincipalId
| order by CountPerManagedIdentity desc
| take 100
```

