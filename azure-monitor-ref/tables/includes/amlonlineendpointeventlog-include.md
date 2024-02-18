---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AmlOnlineEndpointEventLog
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| DeploymentName | string | The name of the deployment associated with this log record. |
| InstanceId | string | The ID of the instance that generated this log record. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | The content of the inference-server container life cycle event. |
| Name | string | The name of the inference-server container life cycle event. |
| OperationName | string | The operation associated with this log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when this log was generated. |
| Type | string | The name of the table |
