---
title: Azure Monitor Logs reference - ADXCommand
description: Reference for ADXCommand table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# ADXCommand

 Azure Data Explorer command execution summary.

## Solutions

- LogManagement
## Resource types

- Azure Data Explorer Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationName | string | application name invoked the command |
| Category | string | The category of this log for this events it will be Command |
| CommandType | string | Command type |
| CorrelationId | string | The client request id |
| DatabaseName | string | The name of the database the command ran on |
| Duration | string | Command duration |
| FailureReason | string | The failure reason |
| LastUpdatedOn | datetime | Time (UTC) at which this command ended |
| OperationName | string | The name of this operation |
| Principal | string | The principal that invoked the query |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceUtilization | dynamic | Command resource utilization |
| RootActivityId | string | The root activity id |
| SourceSystem | string |  |
| StartedOn | datetime | Time (UTC) at which this command started |
| State | string | The State the command ended with |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| Text | string | The text of the invoked command |
| TimeGenerated | datetime | The time (UTC) at which this event was generated |
| TotalCPU | string | Total CPU duration |
| Type | string | The name of the table |
| User | string | The user that invoked the query |
| WorkloadGroup | string | The workload group the command was classified to |
