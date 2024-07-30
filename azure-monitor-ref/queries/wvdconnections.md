---
title: Example log table queries for WVDConnections
description:  Example queries for WVDConnections log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WVDConnections table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Connection Errors  


List connection checkpoints and errors for each connection attempt, along with detailed information across all users.  

```query
//You can also uncomment the where clause to filter to a specific user if you are troubleshooting an issue. 
WVDConnections 
//| where UserName == "upn.here@contoso.com" 
| project-away TenantId,SourceSystem  
| summarize arg_max(TimeGenerated, *), StartTime = min(iff(State=='Started', TimeGenerated , datetime(null) )), ConnectTime = min(iff(State=='Connected', TimeGenerated , datetime(null) )) by CorrelationId  
| join kind=leftouter 
(
    WVDErrors
    |summarize Errors=make_list(pack('Code', Code, 'CodeSymbolic', CodeSymbolic, 'Time', TimeGenerated, 'Message', Message ,'ServiceError', ServiceError, 'Source', Source)) by CorrelationId  
) on CorrelationId
| join kind=leftouter 
(
    WVDCheckpoints
    | summarize Checkpoints=make_list(pack('Time', TimeGenerated, 'Name', Name, 'Parameters', Parameters, 'Source', Source)) by CorrelationId  
    | mv-apply Checkpoints on
    (  
        order by todatetime(Checkpoints['Time']) asc
        | summarize Checkpoints=make_list(Checkpoints)
    )
) on CorrelationId  
| project-away CorrelationId1, CorrelationId2  
| order by TimeGenerated desc
```



### Session duration  


Lists the duration and connection type of each user's connections.  

```query
// The "State" field provides information on the connection stage of an actitivity.
// The delta between "Connected" and "Completed" provides the connection duration.
WVDConnections 
| where State == "Connected"  
| project CorrelationId , UserName, ConnectionType , StartTime=TimeGenerated  
| join kind=inner
(
    WVDConnections  
    | where State == "Completed"  
    | project EndTime=TimeGenerated, CorrelationId
) on CorrelationId  
| project Duration = EndTime - StartTime, ConnectionType, UserName  
| sort by Duration desc
```



### Top 10 users by average connection duration  


Lists 10 users with the longest average connection duration.  

```query
// Connection activities have 3 states, this query demonstrates how to calculate the connection duration.
WVDConnections  
| where State == "Connected"  
| project CorrelationId, UserName, ConnectionType, StartTime=TimeGenerated  
| join kind=inner
(
    WVDConnections  
    | where State == "Completed"  
    | project EndTime=TimeGenerated, CorrelationId
) on CorrelationId  
| project Duration = EndTime - StartTime, ConnectionType, UserName  
| summarize AVGDuration=avg(Duration) by UserName 
| sort by AVGDuration desc 
| limit 10
```



### Top 10 most active users  


Lists top 10 users by total connection duration.  

```query
// The connection duration is the delta between "Connected" and "Completed" state.
WVDConnections 
| where State == "Connected" 
| project CorrelationId , UserName, ConnectionType , StartTime=TimeGenerated 
| join kind=inner
(
    WVDConnections 
    | where State == "Completed" 
    | project EndTime=TimeGenerated, CorrelationId
) on CorrelationId 
| extend SessionDuration = EndTime - StartTime
| summarize TotalConnectionTime = sum(SessionDuration) by UserName, ConnectionType
| top 10 by TotalConnectionTime desc
```



### Average connection duration by hostpool  


Ranks hostpools by average connection duration.  

```query
// Characterize the usage pattern of all hostpools in the current Log Analytics scope
WVDConnections  
| where State == "Connected"
| project ResourceAlias, CorrelationId, StartTime=TimeGenerated, _ResourceId
| join kind = leftouter 
(
    WVDConnections  
    | where State == "Completed"  
    | project EndTime=TimeGenerated, CorrelationId
) on CorrelationId
// If connection hasn't completed yet, it is still running so the end time can be assumed to be now (duration so far)
| project Duration = coalesce(EndTime, now()) - StartTime, _ResourceId
| summarize AvgDuration=avg(Duration) by _ResourceId
| parse _ResourceId with "/subscriptions/" subscription "/resourcegroups/" ResourceGroup "/providers/microsoft.desktopvirtualization/hostpools/" HostPool
| project ResourceGroup, HostPool, AvgDuration
| sort by AvgDuration desc
```



### Client-side operating system information by user count  


Produces a bar chart of operating systems used on client devices connecting to the deployment.  

```query
// Use this query to understand which OS version users have installed on the devices they are connecting from. 
WVDConnections  
| summarize UserCount=dcount(UserName) by ClientOS 
| sort by UserCount desc 
| render barchart
```



### Azure Virtual Desktop client usage information  


List of client types and versions used by users connecting to the deployment.  

```query
WVDConnections  
| summarize UserCount=dcount(UserName) by ClientType, ClientVersion 
| sort by ClientVersion, ClientType, UserCount desc
```



### Average session logon time  


Lists the average session logon time by host pool and session state.  

```query
WVDConnections  
| where TimeGenerated > ago(24h)
| where State == "Started"
| project CorrelationId , UserName, ConnectionType , StartTime=TimeGenerated, _ResourceId
| join kind=inner
(
    WVDConnections
    | where State == "Connected"  
    | project ConnectTime=TimeGenerated, CorrelationId
) on CorrelationId
| join kind=inner
(   
    WVDCheckpoints
    | where Name =~ "LoadBalancedNewConnection"
    | extend LoadBalanceOutcome=tostring(parse_json(Parameters).LoadBalanceOutcome)
) on CorrelationId 
| project Duration = ConnectTime - StartTime, _ResourceId, Session=case(LoadBalanceOutcome in ("Active", "Disconnected"), "ExistingSession", LoadBalanceOutcome == "Pending", "Creating", LoadBalanceOutcome)
// Exclude connections that are happening while another connection kicked off the session creation, since results will be inconclusive
| where Session != "Creating"
| summarize AvgDuration=avg(Duration) by _ResourceId, Session
| parse _ResourceId with "/subscriptions/" subscription "/resourcegroups/" ResourceGroup "/providers/microsoft.desktopvirtualization/hostpools/" HostPool
| project ResourceGroup, HostPool, Session, AvgDuration
| sort by AvgDuration desc
```

