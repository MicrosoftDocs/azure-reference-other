---
ms.service: azure-monitor
ms.topic: include
ms.date: 04/15/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ALBHealthEvent
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Description | string | Description of the health event. |
| FrontendIP | string | Frontend IP of the health event. |
| HealthEventType | string | Type of the health event. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LoadBalancerResourceId | string | Load Balancer Resource Id of the health event. |
| operationName | string | The operation when the record is generated |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Severity | string | Severity of the health event. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
