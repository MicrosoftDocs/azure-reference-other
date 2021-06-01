---
title: Azure Monitor Logs reference - LAQueryLogs
description: Reference for LAQueryLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 6/1/2021
---

# LAQueryLogs

 Audit logs for queries executed in Log Analytics Workspaces.

## Categories

- Audit
## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|AADClientId|string|AAD ClientId used by the caller.|
|AADEmail|string|AAD Email of the caller.|
|AADObjectId|string|AAD ObjectId of the caller.|
|AADTenantId|string|AAD TenantId of the caller.|
|CorrelationId|string|The ID for correlated events.|
|QueryText|string|The full body of the query as submitted by the user.|
|QueryTimeRangeEnd|datetime|The end time (UTC) of the time range across which the query was was requested by the caller to be executed.|
|QueryTimeRangeStart|datetime|The starting time (UTC) of the time range across which the query was was requested by the caller to be executed.|
|RequestClientApp|string|ClientApp string in the request header (x-ms-app).|
|RequestContext|dynamic|ResourceId of all referenced workspaces, applications, and resources across which the query was requested by the caller to be executed.|
|RequestContextFilters|dynamic|Filters applied to the request context.|
|RequestTarget|string|ResourceId of the request URL.|
|ResponseCode|int|The HTTP response code for the request.|
|ResponseDurationMs|real|The duration (in ms) that the query took to execute.|
|ResponseRowCount|int|The number of rows that were returned.|
|SourceSystem|string||
|StatsCPUTimeMs|real|The CPU (in ms) used in the execution of this query.|
|StatsDataProcessedEnd|datetime|The end time (UTC) of the time range across which the data processed.|
|StatsDataProcessedKB|real|The total KB of data that was processed as part of the query.|
|StatsDataProcessedStart|datetime|The starting time (UTC) of the time range across which the data processed.|
|StatsRegionCount|int|The number of regions that the workspaces accessed are spread across.|
|StatsWorkspaceCount|int|The number of workspaces that the query accessed, either explicitly or otherwise.|
|TenantId|string||
|TimeGenerated|datetime|The timestamp (UTC) at which the query was submitted.|
|Type|string|The name of the table|
