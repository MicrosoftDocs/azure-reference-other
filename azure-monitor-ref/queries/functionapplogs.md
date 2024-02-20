---
title: Example log table queries for FunctionAppLogs
description:  Example queries for FunctionAppLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the FunctionAppLogs table


### Show application logs from Function Apps  


A list of application logs, sorted by time (latest logs shown first).  

```query
FunctionAppLogs 
| project TimeGenerated, HostInstanceId, Message, _ResourceId
| sort by TimeGenerated desc
```



### Show logs with warnings or exceptions  


A list of logs which contain warnings or exceptions (latest logs shown first).  

```query
FunctionAppLogs
| where Level == "Warning" or Level == "Error"
| project TimeGenerated, HostInstanceId, Level, Message, _ResourceId
| sort by TimeGenerated desc
```



### Error and exception count  


Show a column chart of the number of the logs containing warnings or errors in the last hour, per application.  

```query
FunctionAppLogs 
| where TimeGenerated > ago(1h)
| where Level == "Warning" or Level == "Error"
| summarize count_per_app = count() by _ResourceId
| sort by count_per_app desc 
| render columnchart
```



### Function activity over time  


Line chart showing trend of Function requests volume, per Function over time.  

```query
FunctionAppLogs
//| where _ResourceId == "MyResourceId" // Uncomment and enter a resource ID to get results for a specific resource
| where Category startswith "Function." and Message startswith "Executed "
| summarize count() by bin(TimeGenerated, 1h), FunctionName // Aggregate by hour
| render timechart
```



### Function results  


Individual Function invocation results in the last hour (latest logs shown first).  

```query
FunctionAppLogs
| where TimeGenerated > ago(1h)
| where Category startswith "Function." and Message startswith "Executed "
| parse Message with "Executed '" Name "' ("  Result ", Id=" Id ", Duration=" Duration:long "ms)"
| project TimeGenerated, FunctionName, Result, FunctionInvocationId, Duration, _ResourceId
| sort by TimeGenerated desc
```



### Function Error rate  


Summarizing functions success and errors per hour.  

```query
FunctionAppLogs
| where Category startswith "Function." and Message startswith "Executed "
| parse Message with "Executed '" Name "' ("  Result ", Id=" Id ", Duration=" Duration:long "ms)"
// | where Name == "MyFunction" // Use this to restrict to a specific function
| summarize count() by bin(TimeGenerated, 1h), Name, Result, _ResourceId
| order by TimeGenerated desc 
```

