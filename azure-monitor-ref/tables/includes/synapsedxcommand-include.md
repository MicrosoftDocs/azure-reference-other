---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SynapseDXCommand
---


| Column | Type | Description |
|---|---|---|
| ApplicationName | string | The name of the application that invoked the command |
| _BilledSize | real | The record size in bytes |
| Category | string | The log category for these events will be 'Command' |
| CommandType | string | Command type. like 'DatabasesShow' |
| CorrelationId | string | The client request ID |
| DatabaseName | string | The name of the database the command ran on |
| Duration | string | Command duration as a string like '00:00:00.0156250' |
| FailureReason | string | The reason for the failure |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastUpdatedOn | datetime | The last time this command was updated |
| Principal | string | Principal that invoked the query like 'aaduser=USER_ID;TENANT' |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceUtilization | dynamic | Resurce consumption for the exuected command |
| RootActivityId | string | The root activity ID |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartedOn | datetime | The time (UTC) when this command started |
| State | string | The state the command ended with, like 'Completed' |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| Text | string | Text of the invoked command |
| TimeGenerated | datetime | The time (UTC) when this event was generated |
| TotalCPU | string | Total CPU runtime across cluster nodes |
| Type | string | The name of the table |
| User | string | User that invoked the query |
| WorkloadGroup | string | Workload are a means of resource governance for incoming requests to the cluster |
