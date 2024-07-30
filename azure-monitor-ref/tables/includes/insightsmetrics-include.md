---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: InsightsMetrics
---


| Column | Type | Description |
|---|---|---|
| AgentId | string | Unique ID of the agent that sourced the metric instance |
| _BilledSize | real | The record size in bytes |
| Computer | string | Computer name/Node name that sourced the metric instance |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Name | string | Name of the metric |
| Namespace | string | Name space/Category of the metric. Ex;- 'container.azm.ms/disk'  |
| Origin | string | Source of the metric. Ex;- 'container.azm.ms/telegraf' |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | string | Dimensions of the metric in json |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
| Val | real | Value of the metric |
| Value | string |   |
