---
title: Example log table queries for Heartbeat
description:  Example queries for Heartbeat log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the Heartbeat table


### Count heartbeats  


Count all computers heartbeats from the last hour.  

```query
// Count computers heartbeats in the last hour. 
// Normally, agents on VMs generate Heartbeat event every minute.
Heartbeat
| where TimeGenerated > ago(1h)
| summarize count() by Computer
```



### Last heartbeat of each computer  


Show the last heartbeat sent by each computer.  

```query
// Last heartbeat of each computer 
// Show the last heartbeat sent by each computer. 
Heartbeat
| summarize arg_max(TimeGenerated, *) by Computer
```



### Ingestion latency (end-to-end) spikes - Heartbeat table  


Check for latency spikes in the ingestion of Heartbeats in the last 24 hours.  

```query
// Ingestion latency (end-to-end) spikes - Heartbeat table 
// Check for latency spikes in the ingestion of Heartbeats in the last 24 hour. 
// This query calculates ingestion duration every 10 minutes, and looks for spikes
let StartTime = ago(24h);
let EndTime = now();
let MinRSquare = 0.9; // Tune the sensitivity of the detection sensor. Higher numbers make the detector more sensitive
Heartbeat
| where TimeGenerated between (StartTime .. EndTime)
// calculate ingestion duration in seconds
| extend IngestionDurationSeconds = (ingestion_time()-TimeGenerated)/1s
// Create a time series
| make-series RatioSeries=avg(IngestionDurationSeconds) default=0 on TimeGenerated in range(StartTime , EndTime,10m)
// Apply a 2-line regression to the time series
| extend (RSquare2, SplitIdx, Variance2, RVariance2, LineFit2) = series_fit_2lines(RatioSeries)
// Find out if our 2-line is trending up or down
|extend (Slope, Interception, RSquare, Variance, RVariance, LineFit) = series_fit_line(LineFit2)
// Check whether the line fit reaches the threshold, and if the spike represents an increase (rather than a decrease)
| project PatternMatch = iff(RSquare2 > MinRSquare and Slope>0, "Spike detected", "No spike")

```



### Agent latency spikes - Heartbeat table  


Check for agent latency spikes in the ingestion of Heartbeats in the last 24 hours.  

```query
// Agent latency spikes - Heartbeat table 
// Check for agent latency spikes in the ingestion of Heartbeats in the last 24 hour. 
// This query calculates ingestion duration every 10 minutes, and looks for spikes
let StartTime = ago(24h);
let EndTime = now();
let MinRSquare = 0.9; // Tune the sensitivity of the detection sensor. Higher numbers make the detector more sensitive
Heartbeat
| where TimeGenerated between (StartTime .. EndTime)
// calculate ingestion duration in seconds
| extend AgentLatencySeconds = (_TimeReceived-TimeGenerated)/1s
// Create a time series
| make-series RatioSeries=avg(AgentLatencySeconds) default=0 on TimeGenerated in range(StartTime , EndTime,10m)
// Apply a 2-line regression to the time series
| extend (RSquare2, SplitIdx, Variance2, RVariance2, LineFit2) = series_fit_2lines(RatioSeries)
// Find out if our 2-line is trending up or down
|extend (Slope, Interception, RSquare, Variance, RVariance, LineFit) = series_fit_line(LineFit2)
// Check whether the line fit reaches the threshold, and if the spike represents an increase (rather than a decrease)
| project PatternMatch = iff(RSquare2 > MinRSquare and Slope>0, "Spike detected", "No spike")
```



### Recently stopped heartbeats - Heartbeat table  


Lists resources that stopped sending heartbeats in past 15 minutes.  

```query
// Resources, which stopped sending heartbeats in last 15 minutes
Heartbeat
| summarize LastReported=now()-max(TimeGenerated) by ResourceGroup, Resource, ResourceType 
// Assuming that heartbeats are sent at least every minute we are looking at 1-15 minute interval
| where LastReported between(1m..15m)
```



### Computers availability today  


Chart the number of computers sending logs, each hour.  

```query
Heartbeat
| summarize dcount(ComputerIP) by bin(TimeGenerated, 1h)
| render timechart
```



### Unavailable computers  


List all known computers that didn't send a heartbeat in the last 5 hours.  

```query
Heartbeat
| summarize LastHeartbeat=max(TimeGenerated) by Computer
| where LastHeartbeat < ago(5h)
```



### Availability rate  


Calculate the availability rate of each connected computer.  

```query
Heartbeat
// bin_at is used to set the time grain to 1 hour, starting exactly 24 hours ago
| summarize heartbeatPerHour = count() by bin_at(TimeGenerated, 1h, ago(24h)), Computer
| extend availablePerHour = iff(heartbeatPerHour > 0, true, false)
| summarize totalAvailableHours = countif(availablePerHour == true) by Computer
| extend availabilityRate = totalAvailableHours*100.0/24
```



### Not reporting VMs  


VMs that have not reported a heartbeat in the last 5 minutes.  

```query
// To create an alert for this query, click '+ New alert rule'
Heartbeat 
| where TimeGenerated > ago(24h)
| summarize LastCall = max(TimeGenerated) by Computer, _ResourceId
| where LastCall < ago(5m)

```



### Computers list  


List of computers with Azure Update Management deployed.  

```query
Heartbeat
| where TimeGenerated>ago(12h) and OSType=="Linux" and notempty(Computer)
| summarize arg_max(TimeGenerated, Solutions, Computer, ResourceId, ComputerEnvironment, VMUUID) by SourceComputerId
| where Solutions has "updates"
| extend vmuuId=VMUUID, azureResourceId=ResourceId, osType=1, environment=iff(ComputerEnvironment=~"Azure", 1, 2), scopedToUpdatesSolution=true, lastUpdateAgentSeenTime=""
| join kind=leftouter
(
   Update
    | where TimeGenerated>ago(5h) and OSType=="Linux" and SourceComputerId in ((Heartbeat
    | where TimeGenerated>ago(12h) and OSType=="Linux" and notempty(Computer)
    | summarize arg_max(TimeGenerated, Solutions) by SourceComputerId
    | where Solutions has "updates"
    | distinct SourceComputerId))
    | summarize hint.strategy=partitioned arg_max(TimeGenerated, UpdateState, Classification, Product, Computer, ComputerEnvironment) by SourceComputerId, Product, ProductArch
    | summarize Computer=any(Computer), ComputerEnvironment=any(ComputerEnvironment), missingCriticalUpdatesCount=countif(Classification has "Critical" and UpdateState=~"Needed"), missingSecurityUpdatesCount=countif(Classification has "Security" and UpdateState=~"Needed"), missingOtherUpdatesCount=countif(Classification !has "Critical" and Classification !has "Security" and UpdateState=~"Needed"), lastAssessedTime=max(TimeGenerated), lastUpdateAgentSeenTime="" by SourceComputerId
    | extend compliance=iff(missingCriticalUpdatesCount > 0 or missingSecurityUpdatesCount > 0, 2, 1)
    | extend ComplianceOrder=iff(missingCriticalUpdatesCount > 0 or missingSecurityUpdatesCount > 0 or missingOtherUpdatesCount > 0, 1, 3)
)
on SourceComputerId
| project id=SourceComputerId, displayName=Computer, sourceComputerId=SourceComputerId, scopedToUpdatesSolution=true, missingCriticalUpdatesCount=coalesce(missingCriticalUpdatesCount, -1), missingSecurityUpdatesCount=coalesce(missingSecurityUpdatesCount, -1), missingOtherUpdatesCount=coalesce(missingOtherUpdatesCount, -1), compliance=coalesce(compliance, 4), lastAssessedTime, lastUpdateAgentSeenTime, osType=1, environment=iff(ComputerEnvironment=~"Azure", 1, 2), ComplianceOrder=coalesce(ComplianceOrder, 2)
| union(Heartbeat
| where TimeGenerated>ago(12h) and OSType=~"Windows" and notempty(Computer)
| summarize arg_max(TimeGenerated, Solutions, Computer, ResourceId, ComputerEnvironment, VMUUID) by SourceComputerId
| where Solutions has "updates"
| extend vmuuId=VMUUID, azureResourceId=ResourceId, osType=2, environment=iff(ComputerEnvironment=~"Azure", 1, 2), scopedToUpdatesSolution=true, lastUpdateAgentSeenTime=""
| join kind=leftouter
(
    Update
    | where TimeGenerated>ago(14h) and OSType!="Linux" and SourceComputerId in ((Heartbeat
    | where TimeGenerated>ago(12h) and OSType=~"Windows" and notempty(Computer)
    | summarize arg_max(TimeGenerated, Solutions) by SourceComputerId
    | where Solutions has "updates"
    | distinct SourceComputerId))
    | summarize hint.strategy=partitioned arg_max(TimeGenerated, UpdateState, Classification, Title, Optional, Approved, Computer, ComputerEnvironment) by Computer, SourceComputerId, UpdateID
    | summarize Computer=any(Computer), ComputerEnvironment=any(ComputerEnvironment), missingCriticalUpdatesCount=countif(Classification has "Critical" and UpdateState=~"Needed" and Approved!=false), missingSecurityUpdatesCount=countif(Classification has "Security" and UpdateState=~"Needed" and Approved!=false), missingOtherUpdatesCount=countif(Classification !has "Critical" and Classification !has "Security" and UpdateState=~"Needed" and Optional==false and Approved!=false), lastAssessedTime=max(TimeGenerated), lastUpdateAgentSeenTime="" by SourceComputerId
    | extend compliance=iff(missingCriticalUpdatesCount > 0 or missingSecurityUpdatesCount > 0, 2, 1)
    | extend ComplianceOrder=iff(missingCriticalUpdatesCount > 0 or missingSecurityUpdatesCount > 0 or missingOtherUpdatesCount > 0, 1, 3)
)
on SourceComputerId
| project id=SourceComputerId, displayName=Computer, sourceComputerId=SourceComputerId, scopedToUpdatesSolution=true, missingCriticalUpdatesCount=coalesce(missingCriticalUpdatesCount, -1), missingSecurityUpdatesCount=coalesce(missingSecurityUpdatesCount, -1), missingOtherUpdatesCount=coalesce(missingOtherUpdatesCount, -1), compliance=coalesce(compliance, 4), lastAssessedTime, lastUpdateAgentSeenTime, osType=2, environment=iff(ComputerEnvironment=~"Azure", 1, 2), ComplianceOrder=coalesce(ComplianceOrder, 2))
| order by ComplianceOrder asc, missingCriticalUpdatesCount desc, missingSecurityUpdatesCount desc, missingOtherUpdatesCount desc, displayName asc
| project-away ComplianceOrder
```



### Find In Heartbeat  


Find in Heartbeat to search for a specific value in the Heartbeat table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
Heartbeat
| where * contains tostring(SearchValue)
| take 1000
```

