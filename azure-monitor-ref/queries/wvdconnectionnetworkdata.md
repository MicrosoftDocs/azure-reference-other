---
title: Example log table queries for WVDConnectionNetworkData
description:  Example queries for WVDConnectionNetworkData log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WVDConnectionNetworkData table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Average round-trip time over time  


Display a graph of round-trip time (in Milliseconds) across all connections in 10 min intervals at the 10th, 50th, and 90th percentiles.  

```query
WVDConnectionNetworkData
| summarize percentiles(EstRoundTripTimeInMs, 90, 50, 10) by bin(TimeGenerated,10m)
| render timechart
```



### Average BW across all connections  


Displays a graph of bandwidth (in Kilobytes per second) across all connections over 10 min intervals at the 10th, 50th, and 90th percentiles.  

```query
WVDConnectionNetworkData
| summarize percentiles(EstAvailableBandwidthKBps, 90, 50, 10) by bin(TimeGenerated,10m)
| render timechart
```



### Top 10 users with the highest round-trip time  


Returns a list of the top 10 users with the highest average round-trip time (in Milliseconds).  

```query
WVDConnectionNetworkData
| join kind=leftouter 
(
    WVDConnections
    | where State == "Completed"
    | distinct CorrelationId, UserName
) on CorrelationId
| summarize AvgRTT=round(avg(EstRoundTripTimeInMs)), RTT_P95=percentile(EstRoundTripTimeInMs, 95) by UserName
| top 10 by AvgRTT desc
```



### Top 10 users with lowest bandwidth  


Returns a list of the top 10 users with the lowest average bandwidth (in Kilobytes per second).  

```query
WVDConnectionNetworkData
| join kind=inner 
(
    WVDConnections
    | where State == "Completed"
    | distinct CorrelationId, UserName
) on CorrelationId
| summarize AvgBW=avg(EstAvailableBandwidthKBps), BW_P95=percentile(EstAvailableBandwidthKBps,95) by UserName
| top 10 by AvgBW asc
```



### Summary of Round-trip time and bandwidth  


Returns the 90th percentiles for round-trip time (in Milliseconds) and bandwidth (in Kilobytes) for each connection along with additional connection details.  

```query
WVDConnectionNetworkData
| summarize RTTP90=percentile(EstRoundTripTimeInMs,90), BWP90=percentile(EstAvailableBandwidthKBps,90), StartTime=min(TimeGenerated), EndTime=max(TimeGenerated) by CorrelationId
| join kind=inner
(
    WVDConnections
    | where State == "Connected"
    | extend Protocol = iif(UdpUse in ("0", "<>"), "TCP", "UDP")
) on CorrelationId
| project CorrelationId, StartTime, EndTime, UserName, SessionHostName, RTTP90, BWP90, Protocol, ClientOS, ClientType, ClientVersion, ConnectionType, ResourceAlias, SessionHostSxSStackVersion
```

