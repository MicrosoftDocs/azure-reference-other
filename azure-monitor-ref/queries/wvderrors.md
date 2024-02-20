---
title: Example log table queries for WVDErrors
description:  Example queries for WVDErrors log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WVDErrors table


### Top 10 connection errors  


Returns the top 10 deployment-side connection errors by user count.  

```query
// You can replace "UserName" in the query by "CorrelationId" to see how many connections each error has impacted.
// The "CorrelationId" is unique for each connection attempt. 
// The flag on "ServiceError" helps to focus on issues that are most likely mitigated by the administrator or end user.
// Change the ActivityType based on the type of issues you are troubleshooting. 
WVDErrors 
| where ServiceError == "false" 
| where ActivityType == "Connection"  
| summarize UserCount = dcount(UserName), SampleMessage = take_any(Message) by CodeSymbolic
| project SampleMessage, UserCount 
| top 10 by UserCount desc
// Go to https://aka.ms/wvdgetstarted and review additional guidance for diagnostics in the How To section.
// Our troubleshooting guidance has information on escalation paths.
```



### Top 10 feed errors  


Returns the top 10 deployment-side feed errors by user count.  

```query
// You can replace "UserName" in the query by "CorrelationId" to see how many feed refresh attempts each error has impacted.
// The "CorrelationId" is unique for each feed refresh attempt. 
// The flag on "ServiceError" helps to focus on issues that are most likely mitigated by the administrator or end user.
// Change the ActivityType based on the type of issues you are troubleshooting. 
WVDErrors 
| where ServiceError == "false" 
| where ActivityType == "Feed"  
| summarize UserCount = dcount(UserName), SampleMessage = take_any(Message) by CodeSymbolic
| project SampleMessage, UserCount 
| top 10 by UserCount desc
// Go to https://aka.ms/wvdgetstarted and review additional guidance for diagnostics in the How To section.
// Our troubleshooting guidance has information on escalation paths.
```

