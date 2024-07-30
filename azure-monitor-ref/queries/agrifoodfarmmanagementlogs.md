---
title: Example log table queries for AgriFoodFarmManagementLogs
description:  Example queries for AgriFoodFarmManagementLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AgriFoodFarmManagementLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Status of farm management operations for a farmer  


Retrieves logs indicating the status (success or failure) for operations performed in the FarmManagement logs category for a farmer.  

```query
AgriFoodFarmManagementLogs
| summarize Count = count() by OperationName, ResultSignature

```



### Status of all operations for a farmer  


Aggregates failures and successes across categories for a farmer.  

```query
((AgriFoodFarmManagementLogs | where FarmerId != "" | summarize AgriFoodFarmManagementLogsCount=count() by FarmerId, ResultType))
| join kind=fullouter (( AgriFoodSatelliteLogs | where FarmerId != "" | summarize AgriFoodSatelliteLogsCount=count() by FarmerId, ResultType)) on FarmerId, ResultType
| join kind=fullouter (( AgriFoodWeatherLogs | where FarmerId != "" | summarize AgriFoodWeatherLogsCount=count() by FarmerId, ResultType)) on FarmerId, ResultType
| join kind=fullouter (( AgriFoodJobProcessedLogs | where FarmerId != "" | summarize AgriFoodJobProcessedLogsCount=count() by FarmerId, ResultType)) on FarmerId, ResultType
| join kind=fullouter (( AgriFoodFarmOperationLogs | where FarmerId != "" | summarize AgriFoodFarmOperationLogsCount=count() by FarmerId, ResultType)) on FarmerId, ResultType
| join kind=fullouter (( AgriFoodInsightLogs | where FarmerId != "" | summarize AgriFoodInsightLogsCount=count() by FarmerId, ResultType)) on FarmerId, ResultType
| join kind=fullouter (( AgriFoodProviderAuthLogs | where FarmerId != "" | summarize AgriFoodProviderAuthLogsCount=count() by FarmerId, ResultType)) on FarmerId, ResultType
| join kind=fullouter (( AgriFoodModelInferenceLogs | where FarmerId != "" | summarize AgriFoodModelInferenceLogsCount=count() by FarmerId, ResultType)) on FarmerId, ResultType
| project FarmerId = coalesce(FarmerId, FarmerId1, FarmerId2, FarmerId3, FarmerId4, FarmerId5, FarmerId6, FarmerId7), AgriFoodFarmManagementLogsCount, AgriFoodSatelliteLogsCount, AgriFoodWeatherLogsCount, AgriFoodJobProcessedLogsCount, AgriFoodFarmOperationLogsCount, AgriFoodInsightLogsCount, AgriFoodProviderAuthLogsCount, AgriFoodModelInferenceLogsCount, ResultType = coalesce(ResultType, ResultType1, ResultType2, ResultType3, ResultType4, ResultType5, ResultType6, ResultType7)

```



### Usage trend for top 100 farmers based on the operations performed  


Retrieves a list of top 100 farmers based on the number of hits received across categories.  

```query
((AgriFoodFarmManagementLogs | where FarmerId != "" | summarize AgriFoodFarmManagementLogsCount=count() by FarmerId))
| join kind=fullouter (( AgriFoodSatelliteLogs | where FarmerId != "" | summarize AgriFoodSatelliteLogsCount=count() by FarmerId)) on FarmerId
| join kind=fullouter (( AgriFoodWeatherLogs | where FarmerId != "" | summarize AgriFoodWeatherLogsCount=count() by FarmerId)) on FarmerId
| join kind=fullouter (( AgriFoodJobProcessedLogs | where FarmerId != "" | summarize AgriFoodJobProcessedLogsCount=count() by FarmerId)) on FarmerId
| join kind=fullouter (( AgriFoodFarmOperationLogs | where FarmerId != "" | summarize AgriFoodFarmOperationLogsCount=count() by FarmerId)) on FarmerId
| join kind=fullouter (( AgriFoodInsightLogs | where FarmerId != "" | summarize AgriFoodInsightLogsCount=count() by FarmerId)) on FarmerId
| join kind=fullouter (( AgriFoodProviderAuthLogs | where FarmerId != "" | summarize AgriFoodProviderAuthLogsCount=count() by FarmerId)) on FarmerId
| join kind=fullouter (( AgriFoodModelInferenceLogs | where FarmerId != "" | summarize AgriFoodModelInferenceLogsCount=count() by FarmerId)) on FarmerId
| project FarmerId = coalesce(FarmerId, FarmerId1, FarmerId2, FarmerId3, FarmerId4, FarmerId5, FarmerId6, FarmerId7), AgriFoodFarmManagementLogsCount, AgriFoodSatelliteLogsCount, AgriFoodWeatherLogsCount, AgriFoodJobProcessedLogsCount, AgriFoodFarmOperationLogsCount, AgriFoodInsightLogsCount, AgriFoodProviderAuthLogsCount, AgriFoodModelInferenceLogsCount
| take 100 

```

