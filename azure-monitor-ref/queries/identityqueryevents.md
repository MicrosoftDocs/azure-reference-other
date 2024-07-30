---
title: Example log table queries for IdentityQueryEvents
description:  Example queries for IdentityQueryEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the IdentityQueryEvents table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### SAMR queries to Active Directory  


Find processes that sent SAMR queries to Active Directory.  

```query
// Find processes that sent SAMR queries to Active Directory
IdentityQueryEvents
| where ActionType == "SAMR query"
//    and isnotempty(AccountName)
| project QueryTime = Timestamp, DeviceName, AccountName, Query, QueryTarget
| join kind=inner (
DeviceProcessEvents
| extend DeviceName = toupper(trim(@"\..*$",DeviceName))
//| where InitiatingProcessCommandLine contains "net.exe"
| project ProcessCreationTime = Timestamp, DeviceName, AccountName,
     InitiatingProcessFileName , InitiatingProcessCommandLine
    ) on DeviceName//, AccountName
| where ProcessCreationTime - QueryTime between (-2m .. 2m)
| project QueryTime, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine, Query, QueryTarget //,AccountName
 | limit 100
```

