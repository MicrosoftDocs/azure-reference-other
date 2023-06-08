---
title: Azure Monitor Logs reference - SynapseDXTableUsageStatistics
description: Reference for SynapseDXTableUsageStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# SynapseDXTableUsageStatistics

 Azure date explorer synapse table usage statistics. Logs include DatabaseName, TableName, User that can be used for monitoring cluster's table usage

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
| _BilledSize | real |  |
| CorrelationId | string | The client request ID |
| DatabaseName | string | Name of the database |
| _IsBillable | string |  |
| MaxCreatedOn | datetime | Lastest extent time of the table |
| MinCreatedOn | datetime | Earliest extent time of the table |
| Principal | string | Principal that invoked the query like 'aaduser=USER_ID;TENANT' |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity ID |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| StartedOn | datetime | The time (UTC) the table usage statistics operation started |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | Name of the table |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) this event was generated |
| Type | string | The name of the table |
| User | string | User that invoked the query |
