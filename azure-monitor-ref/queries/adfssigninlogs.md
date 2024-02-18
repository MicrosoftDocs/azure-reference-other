---
title: Example log table queries for ADFSSignInLogs
description:  Example queries for ADFSSignInLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ADFSSignInLogs table


### Top ADFS account lockouts  


Returns top 10 IP addresses by number of lockouts.  

```query
ADFSSignInLogs
| where TimeGenerated > ago(7d)
| extend errorCode = toint(parse_json(Status).errorCode)
| where errorCode == 300300
| summarize Lockouts = count() by IPAddress
| top 10 by Lockouts
```

