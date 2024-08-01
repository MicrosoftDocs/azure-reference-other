---
title: Example log table queries for SecurityEvent
description:  Example queries for SecurityEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SecurityEvent table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Security Events most common event IDs  


This query displays a descending list of the amount of events ingested per EventId for Security-Auditing.  

```query
SecurityEvent
| where EventSourceName == "Microsoft-Windows-Security-Auditing"
| summarize EventCount = count() by EventID
| sort by EventCount desc

```



### Members added to security groups  


Who was added to security-enabled group over the last day?  

```query
// To create an alert for this query, click '+ New alert rule'
SecurityEvent
| where EventID in (4728, 4732, 4756) // these event IDs indicate a member was added to a security-enabled group
| summarize count() by SubjectAccount, Computer, _ResourceId
// This query requires the Security solution
```



### Uses of clear text password  


List all accounts that logged on using a clear-text password over the last day.  

```query
// To create an alert for this query, click '+ New alert rule'
SecurityEvent
| where EventID == 4624 // event ID 4624: "an account was successfully logged on",
| where LogonType == 8 // logon type 8: "NetworkCleartext"
| summarize count() by TargetAccount, Computer, _ResourceId // count the reported security events for each account
// This query requires the Security solution
```



### Windows failed logins  


Find reports of Windows accounts that failed to login.  

```query
// To create an alert for this query, click '+ New alert rule'
SecurityEvent
| where EventID == 4625
| summarize count() by TargetAccount, Computer, _ResourceId // count the reported security events for each account
// This query requires the Security solution
```



### All Security Activities  


Security activities sorted by time (newest first).  

```query
SecurityEvent
| project TimeGenerated, Account, Activity, Computer
| sort by TimeGenerated desc
```



### Security Activities on the Device  


Security activities on a specific device sorted by time (newest first).  

```query
SecurityEvent 
//| where Computer == "COMPUTER01.contoso.com" // Replace with a specific computer name
| project TimeGenerated, Account, Activity, Computer
| sort by TimeGenerated desc
```



### Security Activities for Admin  


Security activities on a specific device for administrator sorted by time (newest first).  

```query
SecurityEvent 
//| where Computer == "COMPUTER01.contoso.com"  // Replace with a specific computer name
| where TargetUserName == "Administrator"
| project TimeGenerated, Account, Activity, Computer
| sort by TimeGenerated desc
```



### Logon Activity by Device  


Counts logon activities per device.  

```query
SecurityEvent
| where EventID == 4624
| summarize LogonCount = count() by Computer
```



### Devices With More Than 10 Logons  


Counts logon activities per devices with more than 10 logons.  

```query
SecurityEvent
| where EventID == 4624
| summarize LogonCount = count() by Computer
| where LogonCount > 10
```



### Accounts Terminated Antimalware  


Accounts which terminated Microsoft Antimalware.  

```query
SecurityEvent
| where EventID == 4689
| where Process has "MsMpEng.exe" or ParentProcessName has "MsMpEng.exe"
| summarize TerminationCount = count() by Account
```



### Devices with Antimalware Terminated  


Devices which terminated Microsoft Antimalware.  

```query
SecurityEvent
| where EventID == 4689 
| where Process has "MsMpEng.exe" or ParentProcessName has "MsMpEng.exe"
| summarize TerminationCount = count() by Computer
```



### Devices Where Hash Was Executed  


Devices where hash.exe was executed more than 5 times.  

```query
SecurityEvent
| where EventID == 4688
| where Process has "hash.exe" or ParentProcessName has "hash.exe"
| summarize ExecutionCount = count() by Computer
| where ExecutionCount > 5
```



### Process Names Executed  


Lists number of executions per process.  

```query
SecurityEvent
| where EventID == 4688
| summarize ExecutionCount = count() by NewProcessName
```



### Devices With Security Log Cleared  


Devices with securtiy log cleared.  

```query
SecurityEvent
| where EventID == 1102
| summarize LogClearedCount = count() by Computer
```



### Logon Activity by Account  


Logon activity by account.  

```query
SecurityEvent
| where EventID == 4624
| summarize LogonCount = count() by Account
```



### Accounts With Less Than 5 Times Logons  


Logon activity for accounts with less than 5 logons.  

```query
SecurityEvent
| where EventID == 4624
| summarize LogonCount = count() by Account
| where LogonCount < 5
```



### Remoted Logged Accounts on Devices  


Remoted logged accounts on a specific device.  

```query
SecurityEvent
| where EventID == 4624 and (LogonTypeName == "3 - Network" or LogonTypeName == "10 - RemoteInteractive")
//| where Computer == "Computer01.contoso.com" // Replace with a specific computer name
| summarize RemoteLogonCount = count() by Account
```



### Computers With Guest Account Logons  


Computers with logons from guest accounts.  

```query
SecurityEvent
| where EventID == 4624 and TargetUserName == 'Guest' and LogonType in (10, 3)
| summarize count() by Computer
```



### Members Added to Security Enabled Groups  


Members added to the security enabled groups.  

```query
SecurityEvent
| where EventID in (4728, 4732, 4756)
| summarize count() by SubjectAccount
```



### Domain Security Policy Changes  


Counts events of domain policy changed.   

```query
SecurityEvent
| where EventID == 4739
| summarize count() by DomainPolicyChanged
```



### System Audit Policy Changes  


System audit policy changed events by computer.  

```query
SecurityEvent
| where EventID == 4719
| summarize count() by Computer
```



### Suspicious Executables  


Lists suspicious executables.  

```query
SecurityEvent
| where EventID == 8002 and Fqbn == '-'
| summarize ExecutionCountHash=count() by FileHash
| where ExecutionCountHash <= 5
```



### Logons With Clear Text Password  


Logons with clear text password by target account.  

```query
SecurityEvent
| where EventID == 4624 and LogonType == 8
| summarize count() by TargetAccount
```



### Computers With Cleaned Event Logs  


Computers with cleaned event logs.  

```query
SecurityEvent
| where EventID in (1102, 517) and EventSourceName == 'Microsoft-Windows-Eventlog'
| summarize count() by Computer
```



### Accounts Failed to Logon  


Counts failed logons by target account.  

```query
SecurityEvent
| where EventID == 4625
| summarize count() by TargetAccount
```



### Locked Accounts  


Counts locked acounts by target account.  

```query
SecurityEvent
| where EventID == 4740
| summarize count() by TargetAccount
```



### Change or Reset Passwords Attempts  


Counts change/reset paswords attempts per target account.  

```query
SecurityEvent
| where EventID in (4723, 4724)
| summarize count() by TargetAccount
```



### Groups Created or Modified  


Groups created or modified per target account.  

```query
SecurityEvent
| where EventID in (4727, 4731, 4735, 4737, 4754, 4755)
| summarize count() by TargetAccount
```



### Remote Procedure Call Attempts  


Counts remote procedure call attempts per computer.  

```query
SecurityEvent
| where EventID == 5712
| summarize count() by Computer
```



### User Accounts Changed  


Counts user account changes per target account.  

```query
SecurityEvent
| where EventID in (4720, 4722)
| summarize by TargetAccount
```

