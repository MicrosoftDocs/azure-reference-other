---
title: Azure Monitor Logs reference - MicrosoftDynamicsTelemetryPerformanceLogs
description: Reference for MicrosoftDynamicsTelemetryPerformanceLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# MicrosoftDynamicsTelemetryPerformanceLogs

 Microsoft Dynamics Telemetry Performance Logs

## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime|The timestamp (UTC) of the log.|
|Category|string|Log category|
|EnvironmentId|string|Unique identifier for an environment as shown in Lifecycle Services|
|Role|string|Type of the machine (AOS/BI) emitting the events|
|RoleInstance|string|Name of the machine emitting the events|
|EventName|string|Name of the event|
|ActivityId|string|Unique identifier for an activity|
|EventMessage|string|Additional information about the event|
|Pid|int|Process id|
|SqlCpu|real|SqlCpu Utilization|
|Parameters|dynamic|Collection of SQL performance metrics|
|QueryType|string|Type of the executed SQL query|
|ExecutionStatus|int|Execution Status of the query|
|ExecutionResultRowCount|int|Returned rowCount from the executed SQL query|
|ExecutionTimeSeconds|real|Execution time in seconds for the AosDatabaseSlowQuery event|
|SqlStatement|string|SQL query statement|
|CallStack|string|Execution call stack|
|ConnectionType|string|Type of the connection|
|SqlSpid|int|Process id for the SQL statement (SqlSpid)|
|ClassName|string|Name of the class|
|LegalEntity|long|Legal entity|
|BatchJobId|long|Id of the batch job|
|BatchJobTaskId|long|Task Id of the batch job|
|Duration|int|Duration (in milliseconds) of the form execution time|
|DurationInMilliSeconds|int|Duration in milliseconds of the batch jobs|
|Environment|string|Name of the environment as deployed in Lifecycle Services|
|formName|string|Name of the form in Finance and Operations|
|IsValid|bool|Is it valid|
|IsWarmEvent|bool|Is this a warm event|
|ErrorMessage|string|Error message logged in the application |
|CountOfUpdate|int|Count of update requests|
|CountOfDelete|int|Count of delete requests|
|CountOfInsert|int|Count of insert requests|
|CountOfSelect|int|Count of select requests|
|CountOfDdl|int|Count of data definition requests|
|CountOfProc|int|Count of procedure requests|
|CountOfOther|int|Count of other requests|
|TransactionDurationSeconds|real|Transaction duration in seconds for Aos Large Active Transactions|
|Type|string||
|_ResourceId|string||
