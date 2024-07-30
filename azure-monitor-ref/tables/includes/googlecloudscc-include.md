---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: GoogleCloudSCC
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Findings | dynamic | A dynamic array of all the findings associated with the resource. |
| FindingsResource | dynamic | A dynamic array of the resource that was affected by the security finding. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| SourceProperties | dynamic | A map of additional properties about the source of the security finding. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time at which the security finding was first detected. |
| Type | string | The name of the table |
