---
title: Azure Monitor Logs reference - SynapseDXTableUsageStatistics
description: Reference for SynapseDXTableUsageStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
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
| CorrelationId | string | The client request ID |
| DatabaseName | string | Name of the database |
| MaxCreatedOn | datetime | Lastest extent time of the table |
| MinCreatedOn | datetime | Earliest extent time of the table |
| Principal | string | Principal that invoked the query like 'aaduser=USER_ID;TENANT' |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity ID |
| SourceSystem | string |  |
| StartedOn | datetime | The time (UTC) the table usage statistics operation started |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | Name of the table |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) this event was generated |
| Type | string | The name of the table |
| User | string | User that invoked the query |
