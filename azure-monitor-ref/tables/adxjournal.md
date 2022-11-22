---
title: Azure Monitor Logs reference - ADXJournal
description: Reference for ADXJournal table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# ADXJournal

 Azure Data Explorer journal (metadata operations).

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Data Explorer Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ChangeCommand | string | The executed control command that triggered the metadata change |
| CorrelationId | string | The client request ID |
| DatabaseName | string | The name of the database changed following the event |
| EntityContainerName | string | The entity container name (entity=column, container=table), or the database name |
| EntityName | string | The entity name that the operation was executed on, before the change |
| EntityVersion | string | The new metadata version (DB/cluster) following the change |
| Event | string | The metadata change event name |
| OperationTimestamp | datetime | The timestamp (UTC) at which the metadata operation completed |
| OriginalEntityState | string | The state of the entity (entity properties) before the change |
| OriginalEntityVersion | string | The version of the entity (entity properties) before the change |
| Principal | string | The principal (user/app) that executed the control command |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity ID of the operation which caused metadata change (for example: 2217ed0d-888f-4c3d-8776-973471be556e) |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) at which this log was sent to Log Analytics |
| Type | string | The name of the table |
| UpdatedEntityName | string | The new entity name after the change |
| UpdatedEntityState | string | The new state after the change |
| User | string | The user that executed the control command |
