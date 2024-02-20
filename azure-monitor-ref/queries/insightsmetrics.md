---
title: Example log table queries for InsightsMetrics
description:  Example queries for InsightsMetrics log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the InsightsMetrics table


### IoT Edge: Device offline or not sending messages upstream at expected rate  


Identify IoT Edge devices seen in the last 2 days that are not sending D2C messages to IoT Hub at an expected rate during a 30 minute period.  

```query
// To create an alert for this query, click '+ New alert rule'
let targetReceiver = "upstream";
InsightsMetrics
| where Origin == "iot.azm.ms" and Namespace == "metricsmodule"
| where Name == "edgehub_messages_sent_total"
| extend dimensions=parse_json(Tags)
| extend device = tostring(dimensions.edge_device)
| extend target = trim_start(@"[^/]+/", extractjson("$.to", 
tostring(dimensions), typeof(string)))
| where target contains targetReceiver
| extend source = strcat(device, "::", trim_start(@"[^/]+/", 
tostring(dimensions.from)))
| extend messages = toint(Val)
| extend timeUtc = TimeGenerated
| extend sourceTarget = strcat(source, "::", target)
| project timeUtc, source, sourceTarget, messages, device, _ResourceId
| order by device, sourceTarget, timeUtc
| serialize
| extend nextCount = next(messages, 1)
| extend nextSourceTarget= next(sourceTarget, 1)
| extend diff = iff((messages - nextCount) >= 0, messages - nextCount, 0)
| where sourceTarget == nextSourceTarget and diff >= 0
| project TimeGenerated = timeUtc, source, sourceTarget, messages, diff, 
device, _ResourceId
| make-series sum(diff) default=0 on TimeGenerated from ago(2d) to now() 
step 30m by device, _ResourceId
| mv-expand sum_diff, TimeGenerated
| project TimeGenerated=todatetime(TimeGenerated), device, 
AggregatedValue=toint(sum_diff), _ResourceId
```



### IoT Edge: Edge Hub queue size over threshold  


Number of times a device's Edge Hub queue size (sum) was over the configured threshold during the evaluation period.  

```query
// To create an alert for this query, click '+ New alert' 
let qlenThreshold = 100;
InsightsMetrics
| where Origin == "iot.azm.ms" and Namespace == "metricsmodule"
| where Name == "edgehub_queue_length"
| extend dimensions=parse_json(Tags)
| extend device = tostring(dimensions.edge_device)
| extend ep = tostring(dimensions.endpoint)
| extend qlen = toint(Val)
| project device, qlen, ep, TimeGenerated, _ResourceId
| summarize sum(qlen) by TimeGenerated, device, _ResourceId
| where sum_qlen >= qlenThreshold
| project-away sum_qlen
```



### Maximum node disk   


Max node disk usage averaged over 30 mins intervals.  

```query
// To create an alert for this query, click '+ New alert rule'
//InsightMetrics contains all the custom metrics for Container Insights solution
InsightsMetrics // Replace Name with your custom metric
| where Name == "used_percent" and Namespace == "container.azm.ms/disk" 
| summarize val= max(Val) by bin(TimeGenerated, 15m), _ResourceId
| render timechart
```



### Prometheus disk read per second per node  


View Prometheus disk read metrics from the default kubernetes namespace as timechart.  

```query
// To create an alert for this query, click '+ New alert rule'
// Update TimeGenerated field for custom time range
InsightsMetrics
| where Namespace == 'container.azm.ms/diskio'
| where TimeGenerated > ago(1h)
| where Name == 'reads'
| extend Tags = todynamic(Tags)
| extend HostName = tostring(Tags.hostName), Device = Tags.name
| extend NodeDisk = strcat(Device, "/", HostName)
| order by NodeDisk asc, TimeGenerated asc
| serialize //calculating the PreVal, PrevTimeGenerated to render the chart.
| extend PrevVal = iif(prev(NodeDisk) != NodeDisk, 0.0, prev(Val)), PrevTimeGenerated = iif(prev(NodeDisk) != NodeDisk, datetime(null), prev(TimeGenerated))
| where isnotnull(PrevTimeGenerated) and PrevTimeGenerated != TimeGenerated
//Calculating the rate for disk using PreVal
| extend Rate = iif(PrevVal > Val, Val / (datetime_diff('Second', TimeGenerated, PrevTimeGenerated) * 1), iif(PrevVal == Val, 0.0, (Val - PrevVal) / (datetime_diff('Second', TimeGenerated, PrevTimeGenerated) * 1)))
| where isnotnull(Rate)
| project TimeGenerated, NodeDisk, Rate, _ResourceId
| render timechart
```



### Find In InsightsMetrics  


Find in InsightsMetrics to search for a specific value in the InsightsMetrics table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
InsightsMetrics
| where * contains tostring(SearchValue)
| take 1000
```



### What data is being collected?  


List the collected performance counters and object types.  

```query
InsightsMetrics
| where Origin == "vm.azm.ms"
| summarize by Namespace, Name
```



### Virtual Machine available memory  


Virtual Machine available memory.  

```query
InsightsMetrics
| where TimeGenerated > ago(1h)
| where Origin == "vm.azm.ms"
| where Namespace == "Memory"
| where Name == "AvailableMB"
| summarize avg(Val) by bin(TimeGenerated, 5m), Computer
| render timechart 
```



### Chart CPU usage trends by computer  


Calculate CPU usage patterns over the last hour, chart by percentiles.  

```query
InsightsMetrics
| where TimeGenerated > ago(1h)
| where Origin == "vm.azm.ms"
| where Namespace == "Processor"
| where Name == "UtilizationPercentage"
| summarize avg(Val) by bin(TimeGenerated, 5m), Computer //split up by computer
| render timechart
```



### Virtual Machine free disk space   


Show the latest report of free disk space, per instance.  

```query
InsightsMetrics
| where TimeGenerated > ago(1h)
| where Origin == "vm.azm.ms"
| where Namespace == "LogicalDisk"
| where Name == "FreeSpaceMB"
| extend t=parse_json(Tags)
| summarize arg_max(TimeGenerated, *) by tostring(t["vm.azm.ms/mountId"]), Computer // arg_max over TimeGenerated returns the latest record
| project Computer, TimeGenerated, t["vm.azm.ms/mountId"], Val
```



### Track VM Availability using Heartbeat   


Display the VM's reported availability during the last hour.  

```query
InsightsMetrics
| where TimeGenerated > ago(1h)
| where Origin == "vm.azm.ms"
| where Namespace == "Computer"
| where Name == "Heartbeat"
| summarize heartbeat_count = count() by bin(TimeGenerated, 5m), Computer
| extend alive=iff(heartbeat_count > 2, 1.0, 0.0) //computer considered "down" if it has 2 or fewer heartbeats in 5 min interval
| project TimeGenerated, alive, Computer
| render timechart with (ymin = 0, ymax = 1) 
```



### Top 10 Virtual Machines by CPU utilization  


Top 10 Virtual Machines by CPU utilization.  

```query
InsightsMetrics
| where TimeGenerated > ago(1h)
| where Origin == "vm.azm.ms"
| where Namespace == "Processor" and Name == "UtilizationPercentage"
| summarize P90 = percentile(Val, 90) by Computer
| top 10 by P90
```



### Bottom 10 Free disk space %  


Bottom 10 Free disk space % by computer.  

```query
InsightsMetrics
| where TimeGenerated > ago(24h)
| where Origin == "vm.azm.ms"
| where Namespace == "LogicalDisk" and Name == "FreeSpacePercentage"
| summarize P90 = percentile(Val, 90) by Computer
| top 10 by P90 asc
```

