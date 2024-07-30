---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: UAFeedback
---


| Column | Type | Description |
|---|---|---|
| AppName | string |   |
| AppVersion | string |   |
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| Computer | string |   |
| ComputerID | string |   |
| Feedback | string |   |
| FeedbackSubmittedDate | datetime |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MicrosoftResponse | string |   |
| Sentiment | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TimeGenerated | datetime |   |
| Title | string |   |
| TotalUpvotes | int |   |
| Type | string | The name of the table |
