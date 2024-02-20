---
title: Example log table queries for OEPAirFlowTask
description:  Example queries for OEPAirFlowTask log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the OEPAirFlowTask table


### DAG type vs DAG runs summary statitics  


Number of DAG runs of each type of DAG type in the given time range  

```query
OEPAirFlowTask
| extend ResourceName = tostring(split(_ResourceId , '/')[-1])
// | where ResourceName == "<the name of ADME instance>"        // to filter on resourceName replace <...> and uncomment line
| distinct DagName, CorrelationId                               // correlationId is same as runId - we have created a duplicate for consistency in search across logs of all services 
| sort by DagName asc

```



### Correlation IDs of all DAG runs  


Correlation IDs of all the DAG runs that have occurred in the time range (for all DAG types)  

```query
OEPAirFlowTask
| extend ResourceName = tostring(split(_ResourceId , '/')[-1])
// | where ResourceName == "<the name of ADME instance>"        // to filter on resourceName replace <...> and uncomment line
| distinct DagName, CorrelationId                               // correlationId is same as runId - we have created a duplicate for consistency in search across logs of all services 
| summarize count() by DagName

```



### Logs of a DAG run  


Retrieves logs for a particular AirFlow DAG run given the correlationId and time range.  

```query
OEPAirFlowTask
| extend ResourceName = tostring(split(_ResourceId , '/')[-1])
// | where ResourceName == "<the name of ADME instance>"        // to filter on resourceName replace <...> and uncomment line
// | where CorrelationId == "<DAG run's runId>"                 // to filter on correlationID replace <...> with correlationId (same as runId) - we have created a duplicate for to maintain consistency of column name across all services 
| project TimeGenerated, DagName, LogLevel, DagTaskName, CodePath, Content

```



### Error logs of a DAG run  


Retrieves error logs for a particular AirFlow DAG run given the correlationId and time range.  

```query
OEPAirFlowTask
| extend ResourceName = tostring(split(_ResourceId , '/')[-1])
// | where ResourceName == "<the name of ADME instance>"        // to filter on resourceName replace <...> and uncomment line
// | where CorrelationId == "<DAG run's runId>"                 // to filter on correlationID replace <...> with correlationId (same as runId) - we have created a duplicate for to maintain consistency of column name across all services 
| where LogLevel  == "ERROR"
| project TimeGenerated, DagName, LogLevel, DagTaskName, CodePath, Content

```

