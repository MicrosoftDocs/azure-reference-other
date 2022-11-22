---
title: Azure Monitor Logs reference - SynapseDXCommand
description: Reference for SynapseDXCommand table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# SynapseDXCommand

 Azure data explorer synapse command execution summary. Logs include DatabaseName, State, Duration that can be used for monitoring the commands which were invoked on the cluster

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApplicationName | string | The name of the application that invoked the command |
| Category | string | The log category for these events will be 'Command' |
| CommandType | string | Command type. like 'DatabasesShow' |
| CorrelationId | string | The client request ID |
| DatabaseName | string | The name of the database the command ran on |
| Duration | string | Command duration as a string like '00:00:00.0156250' |
| FailureReason | string | The reason for the failure |
| LastUpdatedOn | datetime | The last time this command was updated |
| Principal | string | Principal that invoked the query like 'aaduser=USER_ID;TENANT' |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceUtilization | dynamic | Resurce consumption for the exuected command |
| RootActivityId | string | The root activity ID |
| SourceSystem | string |  |
| StartedOn | datetime | The time (UTC) when this command started |
| State | string | The state the command ended with, like 'Completed' |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| Text | string | Text of the invoked command |
| TimeGenerated | datetime | The time (UTC) when this event was generated |
| TotalCPU | string | Total CPU runtime across cluster nodes |
| Type | string | The name of the table |
| User | string | User that invoked the query |
| WorkloadGroup | string | Workload are a means of resource governance for incoming requests to the cluster |
