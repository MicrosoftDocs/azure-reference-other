---
title: Azure Monitor Logs reference - OLPSupplyChainEvents
description: Reference for OLPSupplyChainEvents table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# OLPSupplyChainEvents

 The events table captures every event that was dispatched from the Open Logistics Platform workspace. Events can be a result of a data plane API call (e.g. Shipment Created, Item Deleted, Notification sent, etc.) or a long running job operation completion (e.g. Data ingestion results in NewDataAvailable event).

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.OpenLogisticsPlatform/Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| CorrelationId | string | Unique identifier to be used to correlate logs with OLPSupplyChainEntityOperations. |
| DurationMs | real | Time it took to service the REST API request, in milliseconds. |
| EventBody | dynamic | The event body. |
| EventId | string | Unique identifier for each event. |
| EventType | string | The type of the event, can be Microsoft.OpenLogisticsPlatform.EntityCreated, Microsoft.OpenLogisticsPlatform.EntityUpdated etc. |
| OperationName | string | The operation name for which the log entry was created. |
| RequestId | string | Unique identifier to be used to correlate request logs. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SupplyChainResourceType | string | The type of supplychain resource for which the event is generated, can be Item, Warehouse, WarehouseItem etc. |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was created. |
| Type | string | The name of the table |
