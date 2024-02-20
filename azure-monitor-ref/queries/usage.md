---
title: Example log table queries for Usage
description:  Example queries for Usage log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the Usage table


### Usage by data types  


Chart the amount of logs reported for each data type, today.  

```query
Usage
| summarize count_per_type=count() by DataType
| sort by count_per_type desc
| render piechart
```



### Billable performance data  


Calculate the volume of billable data (in GB) for Perf data, over the last day.  

```query
Usage
| where TimeGenerated > ago(1d)
| where IsBillable == true
| where DataType == "Perf"
| summarize TotalVolumeGB = sum(Quantity) / 1024
```



### Volume of solutions' data  


Chart the volume of data (in Mb) sent by each solution.  

```query
Usage
| summarize total_MBytes=sum(Quantity) by Solution
| sort by total_MBytes desc nulls last
| render barchart
```



### Total workspace ingestion over the last 24 hours  


Volume (GB) of all data ingested to this workspace, over the last 24 hours.  

```query
Usage
|where TimeGenerated > ago(24h)
|summarize TotalIngestionVolGB = sum(Quantity)/1024.0
```



### Container Insight solution billable data  


See total billable data from Container Insights solution.  

```query
//This includes billable data for all solutions in the workspace, see for Container Insights solution
Usage
| where TimeGenerated > startofday(ago(30d))
| where IsBillable == true
| summarize TotalVolumeGB = sum(Quantity) / 1000 by bin(TimeGenerated, 1d), Solution
| render barchart
```

