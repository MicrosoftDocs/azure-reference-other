---
title: Example log table queries for ApiManagementGatewayLogs
description:  Example queries for ApiManagementGatewayLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ApiManagementGatewayLogs table


### Number of requests  


Count the total number of calls across all APIs in the last 24 hours.  

```query
//Total number of call per resource
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize count(CorrelationId) by _ResourceId 
```



### Logs of the last 100 calls  


Get the logs of the most recent 100 calls in the last 24 hours.  

```query
ApiManagementGatewayLogs
| top 100 by TimeGenerated desc 
```



### Number of calls by APIs  


View the number of calls per API in the last 24 hours.  

```query
//Calls by API ID
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize count(CorrelationId) by ApiId
```



### Bandwidth consumed  


Total bandwidth consumed in the last 24 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| extend bandwidth = RequestSize + ResponseSize 
| summarize sum(bandwidth) by bin(TimeGenerated, 15m), _ResourceId 
| render timechart 
```



### Request sizes  


Statistics of request sizes in the last 24 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize Average=avg(RequestSize), Median=percentile(RequestSize, 50), 90th_Percentile=percentile(RequestSize, 90) by bin(TimeGenerated, 5m) 
| render timechart 
```



### Response sizes  


Statistics of response sizes in the last 24 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize Average=avg(ResponseSize), Median=percentile(ResponseSize, 50), 90th_Percentile=percentile(ResponseSize, 90) by bin(TimeGenerated, 5m) 
| render timechart 
```



### Client TLS versions  


Breakdown of client TLS versions in the last 24 hours.  

```query
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize count(CorrelationId) by ClientTlsVersion, _ResourceId 
```



### Error reasons breakdown  


Breakdown of all error reasons in the last 24 hours.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| where IsRequestSuccess == false
| summarize count(CorrelationId) by LastErrorReason, _ResourceId
```



### Last 100 failed requests  


Get the logs of the last 100 failed requests.  

```query
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| where IsRequestSuccess == false
| top 100 by TimeGenerated desc| where ResponseCode >= 400
```



### Get failed requests due to issues related to the backend  


Get the logs of failed requests due to backend issues.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| where IsRequestSuccess == false
| where BackendResponseCode >= 400
```



### Get failed requests due to issues not related to the backend  


Get the logs of failed requests due to issues not related to the backend (e.g., API Mangement policies configuration, rate limit exceeded, client disconnection).  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| where IsRequestSuccess == false
| where isnull(BackendResponseCode) or BackendResponseCode < 400
| where ResponseCode >= 400
```



### Overall latency  


Statistics of overall latency (in miliseconds) between the time API Mangement starts receiving a request and the time API Management finishes sending the response back to the client.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize Average=avg(TotalTime), Median=percentile(TotalTime, 50), 90th_Percentile=percentile(TotalTime, 90) by bin(TimeGenerated, 15m) 
| render timechart 
```



### Backend latency  


Statistics of time (in miliseconds) spent in backend IO.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize Average=avg(BackendTime), Median=percentile(BackendTime, 50), 90th_Percentile=percentile(BackendTime, 90) by bin(TimeGenerated, 15m) 
| render timechart 
```



### Client latency  


Statistics of time (in miliseconds) spent in client IO.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize Average=avg(ClientTime), Median=percentile(ClientTime, 50), 90th_Percentile=percentile(ClientTime, 90) by bin(TimeGenerated, 15m) 
| render timechart 
```



### Cache hit ratio  


Statistics of Cache hit/miss ratio.  

```query
// To create an alert for this query, click '+ New alert rule'
ApiManagementGatewayLogs
| where TimeGenerated > ago(1d)
| summarize Cache_Miss=countif(Cache  == "miss"), Cache_Hit=countif(Cache == "hit") by bin(TimeGenerated, 15m)
| extend Ratio=Cache_Hit / (Cache_Hit + Cache_Miss)
| project-away Cache_Hit , Cache_Miss 
| render timechart 
```

