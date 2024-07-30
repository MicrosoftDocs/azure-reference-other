---
title: Example log table queries for AzureMetrics
description:  Example queries for AzureMetrics log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AzureMetrics table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Pie chart of HTTP response codes  


Breakdown of response codes for each metric, over the last 12 hours.   

```query
AzureMetrics 
| where TimeGenerated > ago(12h)  
| where MetricName in ("Http2xx", "Http3xx", "Http4xx", "Http5xx") 
| summarize sum(Total) by MetricName  
| render piechart
```



### Line chart of response times  


Time series of mean response time (over 5 minute intervals).  

```query
AzureMetrics 
| extend timeBin = bin(TimeGenerated, 5m) 
| summarize ResponseTime = sumif(Average, MetricName=="AverageResponseTime") by timeBin, bin(TimeGenerated, 1h) 
| sort by TimeGenerated desc 
| render timechart
```



### [Classic] Find In AzureMetrics  


[Classic] Find in AzureMetrics to search for a specific value in the AzureMetrics table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
AzureMetrics
| where * contains tostring(SearchValue)
| take 1000
```



### Latest metrics  


Show the latest metrics reports for each reported metric.  

```query
AzureMetrics 
| summarize arg_max(TimeGenerated, UnitName, Total, Count, Maximum, Minimum, Average) by MetricName
```



### Find In AzureMetrics  


Find in AzureMetrics to search for a specific value in the AzureMetrics table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
AzureMetrics
| where * contains tostring(SearchValue)
| take 1000
```



### ExpressRoute Circuit BitsInPerSecond traffic graph  


Traffic graph BitsInPerSecond (last one hour).  

```query
AzureMetrics
| where MetricName == "BitsInPerSecond"
| summarize by Average, bin(TimeGenerated, 1h), Resource
| render timechart
```



### ExpressRoute Circuit BitsOutPerSecond traffic graph  


Traffic graph BitsOutPerSecond (last one hour).  

```query
AzureMetrics
| where MetricName == "BitsOutPerSecond"
| summarize by Average, bin(TimeGenerated, 1h), Resource
| render timechart
```



### ExpressRoute Circuit ArpAvailablility graph  


Traffic graph for ArpAvailability (5 minutes).  

```query
AzureMetrics
| where MetricName == "ArpAvailability"
| summarize by Average, bin(TimeGenerated, 5m), Resource
| render timechart
```



### ExpressRoute Circuit BGP availability  


Traffic graph for BgpAvailability (5 minutes).  

```query
AzureMetrics
| where MetricName == "BgpAvailability"
| summarize by Average, bin(TimeGenerated, 5m), Resource
| render timechart
```



### Avg CPU usage  


Avg CPU usage in the last hour by resource name.  

```query
//consistently high averages could indicate a customer needs to move to a larger SKU
AzureMetrics
| where ResourceProvider == "MICROSOFT.SQL" // /DATABASES
| where TimeGenerated >= ago(60min)
| where MetricName in ('cpu_percent') 
| parse _ResourceId with * "/microsoft.sql/servers/" Resource  // subtract Resource name for _ResourceId
| summarize CPU_Maximum_last15mins = max(Maximum), CPU_Minimum_last15mins = min(Minimum), CPU_Average_last15mins = avg(Average) by Resource , MetricName
```



### Performance troubleshooting  


Potentially query or deadlock on the system that could lead to poor performance.  

```query
//potentially a query or deadlock on the system that could lead to poor performance
AzureMetrics
| where ResourceProvider == "MICROSOFT.SQL"
| where TimeGenerated >=ago(60min)
| where MetricName in ('deadlock')
| parse _ResourceId with * "/microsoft.sql/servers/" Resource // subtract Resource name for _ResourceId
| summarize Deadlock_max_60Mins = max(Maximum) by Resource, MetricName
```



### Loading Data  


Monitor data loading in the last hour.  

```query
AzureMetrics
| where ResourceProvider == "MICROSOFT.SQL"
| where TimeGenerated >= ago(60min)
| where MetricName in ('log_write_percent')
| parse _ResourceId with * "/microsoft.sql/servers/" Resource// subtract Resource name for _ResourceId
| summarize Log_Maximum_last60mins = max(Maximum), Log_Minimum_last60mins = min(Minimum), Log_Average_last60mins = avg(Average) by Resource, MetricName
```



### P2S connection count  


Active P2S connection count for the last 30 days.  

```query
AzureMetrics 
| where TimeGenerated > ago(30d)
| where MetricName == "P2SConnectionCount"
| summarize by Maximum, bin(TimeGenerated,1h), Resource
| render timechart
```



### P2S bandwidth utilization  


Average P2S bandwidth utilization during the last 12 hours in bits/second.  

```query
AzureMetrics
| where TimeGenerated > ago(24h)
| where MetricName == "P2SBandwidth" 
| summarize by Average, bin(TimeGenerated, 1h), Resource
| render timechart
```



### Gateway throughput  


Aggregate gateway throughput in Bytes/sec.  

```query
AzureMetrics 
| where TimeGenerated > ago(24h)
| where MetricName == "AverageBandwidth"
| summarize by Average, bin(TimeGenerated, 1h), Resource
| render timechart
```



### Show logs from AzureMetrics table  


Lists the latest logs in AzureMetrics table, sorted by time (latest first).  

```query
AzureMetrics
| top 10 by TimeGenerated
```



### Show logs from AzureMetrics table  


Lists the latest logs in AzureMetrics table, sorted by time (latest first).  

```query
AzureMetrics
| top 10 by TimeGenerated
```



### Cluster availability (KeepAlive)  


Display the cluster's availability during the last hour.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureMetrics 
| where ResourceProvider == "MICROSOFT.KUSTO"
| where TimeGenerated > ago(1d)
| where MetricName == "KeepAlive"
| parse _ResourceId with * "providers/microsoft.kusto/clusters/" cluster_name // Get the cluster name from the ResourceId string
| summarize heartbeat_count = count() by bin(TimeGenerated, 30m), cluster_name // bin is used to set the time grain to 30 minutes
| extend alive=iff(heartbeat_count > 0, true, false)
| sort by TimeGenerated asc // sort the results by time (ascending order)
```

