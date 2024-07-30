---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ComputerGroup
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Computer | string | Name of the member computer. |
| Group | string | Name of the group. |
| GroupFullName | string | Full path to the group including the source and source name. |
| GroupId | string | ID of the group. |
| GroupSource | string | Source that group was collected from. Possible values are ActiveDirectory WSUSWSUSClientTargeting. |
| GroupSourceName | string | Name of the source that the group was collected from. For Active Directory this is the domain name. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the computer group was created or updated. |
| Type | string | The name of the table |
