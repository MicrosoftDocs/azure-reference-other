---
title: Example log table queries for WVDAgentHealthStatus
description:  Example queries for WVDAgentHealthStatus log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WVDAgentHealthStatus table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Active sessions on SessionHost  


Display a graph of active sessions.  

```query
let GranularityInterval = 30m; // Time resolution for query results (min value is 30s).
WVDAgentHealthStatus // Fires every ~30s
// Ensure only one data point is provided per host in the pool
| summarize PeakSessionsByHost=max(toint(ActiveSessions)) by SessionHostName, bin(TimeGenerated, 30s), _ResourceId
// Sum up the values for all of the hosts in each pool
| summarize SessionsByHostPool=sum(PeakSessionsByHost) by TimeGenerated, _ResourceId
// Reduce time resolution to desired GranularityInterval and report the peak session count for each pool in that time window
| summarize max(SessionsByHostPool) by bin(TimeGenerated, GranularityInterval), _ResourceId
| render timechart
```



### HealthChecks of SessionHost  


Renders a summary of SessionHost health status.  

```query
let HealthCheckIdToDescription = (idx:long) {
    case(
        idx == 0,  "DomainJoin",
        idx == 1,  "DomainTrust",
        idx == 2,  "FSLogix",
        idx == 3,  "SxSStack",
        idx == 4,  "URLCheck",
        idx == 5,  "GenevaAgent",
        idx == 6,  "DomainReachable",
        idx == 7,  "WebRTCRedirector",
        idx == 8,  "SxSStackEncryption",
        idx == 9,  "IMDSReachable",
        idx == 10, "MSIXPackageStaging",
        strcat("InvalidNameIndex: ", idx)
     )
};
let GetHealthCheckResult = (idx:long) {
    case(
        idx == 0, "Unknown",
        idx == 1, "Succeeded",
        idx == 2, "Failed",
        idx == 3, "SessionHostShutdown",
        strcat("InvalidResultIndex: ", idx)
    )
};
WVDAgentHealthStatus
// In some states (e.g. Unavailable, Upgrading) hosts are not running health checks
| where isnotempty(SessionHostHealthCheckResult)
| mv-expand SessionHostHealthCheckResult to typeof(dynamic)
| evaluate bag_unpack(SessionHostHealthCheckResult)
| evaluate bag_unpack(AdditionalFailureDetails)
| extend HealthCheckDesc = HealthCheckIdToDescription(HealthCheckName)
| summarize count(), FirstSeen=min(TimeGenerated), LastSeen=max(TimeGenerated) by HealthCheckDesc, SessionHostName, HealthCheckResult=GetHealthCheckResult(HealthCheckResult)
```

