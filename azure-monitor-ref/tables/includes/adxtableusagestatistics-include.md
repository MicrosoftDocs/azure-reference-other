---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ADXTableUsageStatistics
---


| Column | Type | Description |
|---|---|---|
| ApplicationName | string | The name of the application that invoked the command |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The client request ID |
| DatabaseName | string | The name of the database |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MaxCreatedOn | datetime | Lastest extent time of the table |
| MinCreatedOn | datetime | Oldest extent time of the table |
| OperationName | string | The name of this operation |
| Principal | string | The principal that invoked the query |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RootActivityId | string | The root activity ID |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartedOn | datetime | Time (UTC) at which table usage statistics operation started |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TableName | string | The name of the table |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) at which this event was generated |
| Type | string | The name of the table |
| User | string | The user that invoked the query |
