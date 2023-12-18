---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ArcK8sControlPlane
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | Service log category describing the service logging the message. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Level (Fatal, Error, Warning, Info) of the log message. |
| Message | string | Log message body. |
| PodName | string | Name of the pod logging the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Stream | string | Output stream (stdout, stderr) source of the log message. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Event generation time. |
| Type | string | The name of the table |
