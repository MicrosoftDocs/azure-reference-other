---
title: Example log table queries for IdentityLogonEvents
description:  Example queries for IdentityLogonEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the IdentityLogonEvents table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### LDAP authentication processes with cleartext passwords  


Find processes that performed LDAP authentication with cleartext passwords.  

```query
// Find processes that performed LDAP authentication with cleartext passwords
IdentityLogonEvents
| where Protocol == "LDAP" //and isnotempty(AccountName)
| project LogonTime = Timestamp, DeviceName, Application, ActionType, LogonType //,AccountName
| join kind=inner (
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess"
| extend DeviceName = toupper(trim(@"\..*$",DeviceName))
| where RemotePort == "389"
| project NetworkConnectionTime = Timestamp, DeviceName, AccountName = InitiatingProcessAccountName, InitiatingProcessFileName, InitiatingProcessCommandLine
) on DeviceName
| where LogonTime - NetworkConnectionTime between (-2m .. 2m)
| project Application, LogonType, ActionType, LogonTime, DeviceName, InitiatingProcessFileName, InitiatingProcessCommandLine //, AccountName
| limit 100
```

