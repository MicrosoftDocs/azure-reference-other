---
title: Example log table queries for SigninLogs
description:  Example queries for SigninLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SigninLogs table


### All SiginLogs events  


All Azure signin events.  

```query
SigninLogs
| project UserDisplayName, Identity,UserPrincipalName,  AppDisplayName, AppId, ResourceDisplayName
```



### Resources accessed by user  


Lists the resources accessed for a specific user.  

```query
// Set v_Users_UPN with the UPN of the user of interest
let v_Users_UPN = "osotnoc@contoso.com";
SigninLogs
| where UserPrincipalName == v_Users_UPN
| summarize Count=count()  by ResourceDisplayName, AppDisplayName
```



### User count per Resource  


Distinct count if users by resource.  

```query
SigninLogs
| project UserDisplayName, Identity,UserPrincipalName,  AppDisplayName, AppId, ResourceDisplayName
| summarize UserCount=dcount(UserPrincipalName) by ResourceDisplayName
```



### User count per Application  


Distinct count of users by application.  

```query
SigninLogs
| project UserDisplayName, Identity,UserPrincipalName,  AppDisplayName, AppId, ResourceDisplayName
| summarize UserCount=dcount(UserPrincipalName) by AppDisplayName
```



### Failed Signin reasons  


The query list the main reasons for sign in failures.  

```query
SigninLogs
| where ResultType != 0
| summarize Count=count() by ResultDescription, ResultType
| sort by Count desc nulls last
```



### Failed MFA challenge  


Highlights sign in failures caused by failed MFA challenge.  

```query
SigninLogs
| where ResultType == 50074
| project UserDisplayName, Identity,UserPrincipalName, ResultDescription,  AppDisplayName, AppId, ResourceDisplayName
| summarize FailureCount=count(), FailedResources=dcount(ResourceDisplayName), ResultDescription=any(ResultDescription) by UserDisplayName
```



### Failed App tried silent signin  


Failed silent app signin attempts.  

```query
SigninLogs
| where ResultType == 50058
| project UserDisplayName, Identity,UserPrincipalName, ResultDescription,  AppDisplayName, AppId, ResourceDisplayName
| summarize FailureCount=count(), FailedResources=dcount(ResourceDisplayName), ResultDescription=any(ResultDescription) by UserDisplayName
```



### Failed login Count  


Resources with most failed log in attempts.  

```query
SigninLogs
| where ResultType !=0
| summarize FailedLoginCount=count() by ResourceDisplayName
| sort by FailedLoginCount desc nulls last
```



### Signin Locations  


Failed and successful sig ins by source location.  

```query
SigninLogs
| summarize Successful=countif(ResultType==0), Failed=countif(ResultType!=0) by Location
```



### Logins To Resource  


Lists API sign ins.  

```query
SigninLogs
| where ResourceDisplayName == "Windows Azure Service Management API"
| project TimeGenerated, UserDisplayName, Identity,UserPrincipalName,  AppDisplayName, Success=iff(ResultType==0, "Success", "Fail")
```

