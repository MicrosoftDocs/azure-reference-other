---
title: Example log table queries for Event
description:  Example queries for Event log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the Event table


### Memory usage percentage  


For your cluster view avg node memory usage percentage.  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID
//Unit for MemoryUsage is in percentage(%),TotalMemory, and UsedMemory are in bytes
//Please use Nodename to set alert for each node
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3000"
| extend ClusterData = parse_xml(EventData)
| extend ClusterName = tostring(ClusterData.DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(ClusterData.DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend servers_information = parse_json(RenderedDescription).m_servers
| mv-expand servers_information
| extend Nodename = tostring(servers_information.m_name)
| extend TotalMemory = todecimal(servers_information.m_totalPhysicalMemoryInBytes)
| extend UsedMemory = iff(TotalMemory == 0.0, todecimal(0.0), todecimal(servers_information.m_usedPhysicalMemoryInBytes))
| extend MemoryUsage = iff(TotalMemory == 0.0, todecimal(0.0), todecimal(round(UsedMemory / TotalMemory * 100, 0)))

```



### Avg node CPU usage percentage  


For your cluster view avg node CPU usage percentage.  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID
//Unit for UsedCpuPercentage is in percentage(%)
//Please use Nodename to set alert for each node
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3000"
| extend ClusterData = parse_xml(EventData)
| extend ClusterName = tostring(ClusterData.DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(ClusterData.DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend servers_information = parse_json(RenderedDescription).m_servers
| mv-expand servers_information
| extend Nodename = tostring(servers_information.m_name)
| extend UsedCpuPercentage = toint(servers_information.m_totalProcessorsUsedPercentage)

```



### Virtual machines failed  


For your cluster, view failed virtual machines in a cluster.  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3003"
| extend ClusterName = tostring(parse_xml(EventData).DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(parse_xml(EventData).DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend description = parse_json(RenderedDescription)
| extend VmsFailed = toint(description.m_totalVmsFailed)

```



### Total virtual machines in a cluster.  


For your cluster, view total, running, stopped and failed virtual machines in a cluster  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3003"
| extend ClusterName = tostring(parse_xml(EventData).DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(parse_xml(EventData).DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend description = parse_json(RenderedDescription)
| extend VmsStopped = toint(description.m_totalVmsStopped)
```



### Available volume capacity in a cluster.  


View available capacity (in Bytes) for a volume in a cluster  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID 
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3002"
| extend ClusterData = parse_xml(EventData)
| extend ClusterName = tostring(ClusterData.DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(ClusterData.DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend volumes_information = parse_json(RenderedDescription).VolumeList
| mv-expand volumes_information
| extend Volumes = tostring(volumes_information.m_Label)
| extend TotalCap = todecimal(volumes_information.m_Size)
| extend AvailableCap = TotalCap - todecimal(volumes_information.m_SizeUsed)
```



### Volume latency  


This query shows the latency for your volumes.  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3002"
| extend ClusterData = parse_xml(EventData)
| extend ClusterName = tostring(ClusterData.DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(ClusterData.DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend volumes_information = parse_json(RenderedDescription).VolumeList
| mv-expand volumes_information
| extend VolumeName = tostring(volumes_information.m_Label)
| extend Latency = todouble(volumes_information.m_AverageLatency)
| extend Latency = iff(Latency < 0, 0.0, Latency)
```



### Volume IOPS  


This query shows the input output operations per second for your volumes in a cluster.  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID to view IOPS of volumes in a cluster
//Unit for IOPS will be IOPS/s
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3002"
| extend ClusterData = parse_xml(EventData)
| extend ClusterName = tostring(ClusterData.DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(ClusterData.DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend volumes_information = parse_json(RenderedDescription).VolumeList
| mv-expand volumes_information
| extend VolumesName = tostring(volumes_information.m_Label)
| extend Iops = todouble(volumes_information.m_TotalIops)
| extend Iops = iff(Iops < 0, 0.0, Iops)
```



### Volume throughput  


This query shows the throughput for your volumes in a cluster.  

```query
//Select your log analytics workspace and replace enter cluster ID with your cluster arm ID
//Unit for throughput is B/s
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3002"
| extend ClusterData = parse_xml(EventData)
| extend ClusterName = tostring(ClusterData.DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(ClusterData.DataItem.UserData.EventData["ArmId"])
| where ClusterArmId =~ 'enter cluster ID'
| summarize arg_max(TimeGenerated, RenderedDescription)
| extend volumes_information = parse_json(RenderedDescription).VolumeList
| mv-expand volumes_information
| extend VolumeName = tostring(volumes_information.m_Label)
| extend Throughput = todouble(volumes_information.m_TotalThroughput)
| extend Throughput = iff(Throughput < 0, 0.0, Throughput)

```



### Cluster node down  


Get an alert if a node is down within a cluster.  

```query
//Select your log analytics workspace and replace clusterarmId1 with your cluster arm ID
//Please split dimensions by clusterarmID and dimension name as faulting resource ID to set up alerts for each node within a cluster. Please check include all future values to get alerts for future dimension names.
Event
| where EventLog =~ "Microsoft-Windows-Health/Operational"
| extend description = parse_json(RenderedDescription)
| extend CorrelationId = tostring(description.CorrelationId)
| join kind=leftsemi (Event
    | where EventLog =~ "Microsoft-Windows-Health/Operational"
    | extend description = parse_json(RenderedDescription)
    | extend ClusterArmId = tostring(description.ArmId)
    //| where ClusterArmId in~ ('clusterarmId1', 'clusterarmId2', 'clusterarmId3')
    | where tostring(description.IsLastMessage) =~ 'true'
    | extend CorrelationId = tostring(description.CorrelationId)
    | summarize arg_max(TimeGenerated, *) by ClusterArmId
    | project CorrelationId)
    on CorrelationId
| extend ClusterArmId = tostring(description.ArmId)
| where tostring(description.Fault.RootObjectType) == 'Microsoft.Health.EntityType.Cluster'
| extend Fault = description.Fault
| extend ShortDescription = split(tostring(Fault.Type), '.')[-1]
| extend Faulttype= Fault.Type
| where Faulttype == "Microsoft.Health.FaultType.Server.Down"
| extend Severity = toint(Fault.Severity)
| extend FaultingResourceType = split(tostring(Fault.ObjectType), '.')[-1]
| extend FaultingResourceId = tostring(Fault.ObjectId)
| extend ReportedTime = datetime_add('Microsecond', tolong(Fault.Timestamp) / 10, make_datetime(1601, 1, 1))
| extend Detail = pack(
    "Severity", iff(Severity == 0, "Healthy", iff(Severity == 1, "Warning", iff(Severity == 2, "Critical", "Unknown"))),
    "Faulting Resource ID", FaultingResourceId,
    "Faulting Resource Type", FaultingResourceType,
    "Faulttype", Faulttype,
    "Reported Time", ReportedTime,
    "Short Description", ShortDescription,
    "Description", tostring(Fault.Description),
    "clusterARMId", tostring(ClusterArmId),
    "Remediation", tostring(Fault.Remediation))
| sort by ReportedTime asc
| limit 100
```



### Memory usage percentage  


For your cluster view avg node memory usage percentage.  

```query
//Select your log analytics workspace and replace clusterarmId1 with your cluster arm ID
//Unit for MemoryUsage is in percentage(%),TotalMemory, and UsedMemory are in bytes
Event
| where EventLog =~ "Microsoft-Windows-SDDC-Management/Operational" and EventID == "3000"
| extend ClusterData = parse_xml(EventData)
| extend ClusterName = tostring(ClusterData.DataItem.UserData.EventData["ClusterName"])
| extend ClusterArmId = tostring(ClusterData.DataItem.UserData.EventData["ArmId"])
//| where ClusterArmId in~ ('clusterarmId1', 'clusterarmId2', 'clusterarmId3')
| summarize arg_max(TimeGenerated, *) by ClusterArmId
| extend servers_information = parse_json(RenderedDescription).m_servers
| mv-expand servers_information
| extend Nodename = tostring(servers_information.m_name)
| extend TotalMemory = todecimal(servers_information.m_totalPhysicalMemoryInBytes)
| extend UsedMemory = iff(TotalMemory == 0.0, todecimal(0.0), todecimal(servers_information.m_usedPhysicalMemoryInBytes))
| extend MemoryUsage = iff(TotalMemory == 0.0, todecimal(0.0), todecimal(round(UsedMemory / TotalMemory * 100, 0)))
| extend MemoryUsageint = toint(MemoryUsage)
| where Nodename != ""
| limit 100
```



### Ingestion latency (end-to-end) timechart - Event table  


Chart the latency of ingestion to the Event table in the last 1 day.  

```query
Event
| where TimeGenerated > ago(1d)
| project TimeGenerated, IngestionDurationSeconds = (ingestion_time()-TimeGenerated)/1s
| render timechart title = "Ingestion latency: Event table" 
```



### Show the trend of a selected event  


Chart how many times an event was reported along the last day.  

```query
// To create an alert for this query, click '+ New alert rule'
Event
| where EventID == 44 // this ID indicates Windows Update started downloading an update
| summarize count() by bin(TimeGenerated, 1h), Computer, _ResourceId // bin is used to set the time grain to 1 hour
| render barchart
```



### Error event on computer missing security co critical update  


Error events for machines that are missing critical or security required updates.  

```query
// To create an alert for this query, click '+ New alert rule'
Event
| where EventLevelName == "error"
    | join kind=inner (Update |where (Classification == "Security Updates" or Classification == "Critical Updates") and UpdateState == "Needed" and Optional == "false" | distinct Computer) on Computer 
    | sort by TimeGenerated desc
```



### All Events in the past hour  


All Events in the past hour.  

```query
Event
| where TimeGenerated > ago(1h)
| sort by TimeGenerated desc
```



### Events started  


Events started by event ID.  

```query
Event
| where RenderedDescription contains "started" 
| summarize count() by EventID
```



### Events by event source  


Events by event source.  

```query
Event
| summarize count() by Source
```



### Events by event ID  


Top 10 events by event ID.  

```query
Event 
| summarize count() by EventID
| top 10 by count_
```



### Warning events  


Warning events sortd by time.  

```query
Event 
| where EventLevelName == "warning" 
| sort by TimeGenerated desc
```



### Count of warning events  


Count of warning events by event ID.  

```query
Event 
| where EventLevelName == "warning" 
| summarize count() by EventID
```



### Events in OM between 2000 to 3000  


Operation manger events with IDs in range of 2000 to 3000.  

```query
Event 
| where EventLog == "Operations Manager" and (EventID >= 2000 and EventID <= 3000) 
| sort by TimeGenerated desc
```



### Windows Fireawall policy settings  


Windows Fireawall policy settings changed.  

```query
Event
| where EventLog == "Microsoft-Windows-Windows Firewall With Advanced Security/Firewall" and EventID == 2008 
| sort by TimeGenerated desc
```



### Windows Fireawall policy settings changed by machines  


Windows Fireawall policy settings changed by machines.  

```query
Event 
| where EventLog == "Microsoft-Windows-Windows Firewall With Advanced Security/Firewall" and EventID == 2008 
| summarize count() by Computer 
| limit 10000
```

