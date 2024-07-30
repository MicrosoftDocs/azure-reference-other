---
title: Example log table queries for Perf
description:  Example queries for Perf log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the Perf table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Non-RDMA activity  


View Non-RDMA activity of a node within a cluster.  

```query
//Select your log analytics workspace and replace enter nodename with the name of the node within a cluster on which you want to set the alert for Non-RDMA activity
Perf
| where ObjectName == "Network Interface"
| extend Nodename= tostring(split(Computer, ".")[0])
| where Nodename =~'enter nodename'
| summarize NetworkUsage = sum(CounterValue), Nodename = any(Nodename) by TimeGenerated
| summarize arg_max(TimeGenerated, Nodename, NetworkUsage)
```



### RDMA activity  


View RDMA activity of a node within a cluster.  

```query
//Select log analytics workspace and replace enter nodename with the name of the node within a cluster on which you want to set the alert for RDMA activity
Perf
| where ObjectName == "RDMA Activity"
| extend Nodename= tostring(split(Computer, ".")[0])
| where Nodename =~'enter nodename'
| summarize RdmaUsage = sum(CounterValue), Nodename = any(Nodename) by TimeGenerated
| summarize arg_max(TimeGenerated, Nodename, RdmaUsage)
```



### What data is being collected?  


List the collected performance counters and object types (Process, Memory, Processor).  

```query
Perf
| summarize by ObjectName, CounterName
```



### Memory and CPU usage  


Chart all computers' used memory and CPU, over the last hour.  

```query
Perf
| where TimeGenerated > ago(1h)
| where (CounterName == "% Processor Time" and InstanceName == "_Total") or CounterName == "% Used Memory"
| project TimeGenerated, CounterName, CounterValue
| summarize avg(CounterValue) by CounterName, bin(TimeGenerated, 1m)
| render timechart
```



### CPU usage trends over the last day  


Calculate CPU usage patterns across all computers, chart by percentiles.  

```query
Perf
| where ObjectName == "Processor" and CounterName == "% Processor Time" and InstanceName == "_Total"
| summarize percentiles(CounterValue, 50, 90, 99) by bin(TimeGenerated, 1h)
| render timechart
```



### Top 10 computers with the highest disk space  


Show the top 10 computers with the highest available disk space.  

```query
Perf
| where CounterName == "Free Megabytes" and InstanceName == "_Total"
| summarize arg_max(TimeGenerated, *) by Computer
| top 10 by CounterValue
```



### What data is being collected?  


List the collected performance counters and object types (Process, Memory, Processor…)  

```query
Perf
| summarize by ObjectName, CounterName
```



### Virtual Machine available memory  


Chart the VM's available memory over time.  

```query
// To create an alert for this query, click '+ New alert rule'
Perf
| where ObjectName == "Memory" and
(CounterName == "Available MBytes Memory" or // the name used in Linux records
CounterName == "Available MBytes") // the name used in Windows records
|  summarize avg(CounterValue) by bin(TimeGenerated, 15min), Computer, _ResourceId // bin is used to set the time grain to 15 minutes
| render timechart
```



### Chart CPU usage trends  


Calculate CPU usage patterns over the last day, chart by percentiles.  

```query
// To create an alert for this query, click '+ New alert rule'
Perf
| where CounterName == "% Processor Time"
| where ObjectName == "Processor"
| summarize avg(CounterValue) by bin(TimeGenerated, 15min), Computer, _ResourceId // bin is used to set the time grain to 15 minutes
| render timechart
// Perf table stores performance counters for Windows and Linux computers
// Counters are specified using ObjectName (performance object), InstanceName and CounterName
// % Processor Time captures CPU activity, ObjectNames can be Processor, Process and Process Information
```



### Virtual Machine free disk space  


Show the latest report of free disk space, per instance.  

```query
// To create an alert for this query, click '+ New alert rule'
Perf
| where ObjectName == "LogicalDisk" or // the object name used in Windows records
ObjectName == "Logical Disk" // the object name used in Linux records
| where CounterName == "Free Megabytes"
| summarize arg_max(TimeGenerated, *) by InstanceName // arg_max over TimeGenerated returns the latest record
| project TimeGenerated, InstanceName, CounterValue, Computer, _ResourceId
```



### Top 10 Virtual Machines by CPU utilization  


Find top 10 VM by CPU utilization in the last 7 days.  

```query
Perf
| where TimeGenerated > ago(7d)
| where CounterName == "% Processor Time" and InstanceName == "_Total" 
| project TimeGenerated, Computer, ObjectName, CounterName, InstanceName, round(CounterValue, 2)
| summarize arg_max(TimeGenerated, *) by Computer
| top 10 by CounterValue
```



### Bottom 10 Free disk space %  


Bottom 10 Free disk space % by computer, for the last 7 days.  

```query
Perf
| where TimeGenerated > ago(7d)
| where (ObjectName == "Logical Disk" or ObjectName == "LogicalDisk") and CounterName contains "%" and InstanceName != "_Total" and InstanceName != "HarddiskVolume1"
| project TimeGenerated, Computer, ObjectName, CounterName, InstanceName, CounterValue 
| summarize arg_max(TimeGenerated, *) by Computer
| top 10 by CounterValue desc
```



### Container CPU  


View all the container CPU usage averaged over 30mins.  

```query
// To create an alert for this query, click '+ New alert rule'
//Select the Line chart display option: can we calculate percentage?
Perf
| where ObjectName == "K8SContainer" and CounterName == "cpuUsageNanoCores"
| summarize AvgCPUUsageNanoCores = avg(CounterValue) by bin(TimeGenerated, 30m), InstanceName, _ResourceId
```



### Container memory  


View container CPU averaged over 30 mins intervals.  

```query
// To create an alert for this query, click '+ New alert rule'
//Select the Line chart display option: can we calculate percentage?
let threshold = 75000000; // choose a threshold 
Perf
| where ObjectName == "K8SContainer" and CounterName == "memoryRssBytes"
| summarize AvgUsedRssMemoryBytes = avg(CounterValue) by bin(TimeGenerated, 30m), InstanceName, _ResourceId
| where AvgUsedRssMemoryBytes > threshold 
| render timechart
```



### Instances Avg CPU usage growth from last week  


Show Avg CPU growth by instance in the last week by descending order.  

```query
// To create an alert for this query, click '+ New alert rule'
//Show which instances grew CPU usage from last week to current
Perf
| where TimeGenerated > ago(7d) //This week Average CPU Usage Nano Cores
| where ObjectName == "K8SContainer" and CounterName == "cpuUsageNanoCores"
| summarize ThisWeekAvgCPU = avg(CounterValue) by InstanceName, _ResourceId
| join kind= leftouter (
    //Previous week Average CPU Usage Nano Cores
    Perf
    | where TimeGenerated > ago(14d) and TimeGenerated <= ago(7d)
    | where ObjectName == "K8SContainer" and CounterName == "cpuUsageNanoCores"
    | summarize PrevWeekAvgCPU = avg(CounterValue) by InstanceName, _ResourceId
) on InstanceName, _ResourceId
| extend InstanceNameParts = split(InstanceName, "/")  //array of the parts of the instance name
| extend ShortInstanceName = InstanceNameParts[(array_length(InstanceNameParts)-1)] //extract the last part of the instance name
| extend ThisWeekAvgCPU = round(ThisWeekAvgCPU,0) 
| extend PrevWeekAvgCPU = round(iff(isempty(PrevWeekAvgCPU),0.0,PrevWeekAvgCPU),0) //When doing join with kind=leftouter, missing matches has empty value. To calculate growth, it should be converted to zero. In this case, empty value means that instance did not exist in the previous week
| extend AvgCPUGrowth = round(ThisWeekAvgCPU - PrevWeekAvgCPU , 0) //Calculate growth
| project-away InstanceName1,InstanceNameParts //Remove redundant fields
| order by AvgCPUGrowth desc 
```



### Find In Perf  


Find in Perf to search for a specific value in the Perf table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
Perf
| where * contains tostring(SearchValue)
| take 1000
```

