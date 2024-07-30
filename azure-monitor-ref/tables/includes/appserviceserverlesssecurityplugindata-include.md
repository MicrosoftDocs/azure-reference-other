---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AppServiceServerlessSecurityPluginData
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Index | int | Available when multiple payloads exist for the same message. In that case, payloads share the same SlSecRequestId and Index defines the chronological order of payloads. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MsgVersion | string | The version of the message schema. Used to make code changes backward- and forward- compatible. |
| Payload | dynamic | An array of messages, where each one is a JSON string. |
| PayloadType | string | The type of the payload. Mostly used to distinguish between messages meant for different types of security analysis. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Sender | string | The name of the component that published this message. Almost always will be the name of the plugin, but can also be platform. |
| SlSecMetadata | dynamic | Contains details about the resource like the deployment ID, runtime info, website info, OS, etc. |
| SlSecProps | dynamic | Contains other details that might be needed for debugging end-to-end requests, e.g., slsec nuget version. |
| SlSecRequestId | string | The ingestion request ID used for identifying the message and the request for diagnostics and debugging. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time (UTC) this message was created on the node. |
| Type | string | The name of the table |
