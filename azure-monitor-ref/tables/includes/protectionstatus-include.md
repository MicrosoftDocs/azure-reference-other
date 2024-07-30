---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: ProtectionStatus
---


| Column | Type | Description |
|---|---|---|
| AMProductVersion | string |   |
| _BilledSize | real | The record size in bytes |
| Computer | string |   |
| ComputerEnvironment | string |   |
| ComputerIP_Hidden | string |   |
| DetectionId | string |   |
| DeviceName | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ManagementGroupName | string |   |
| OSName | string |   |
| ProtectionStatus | string |   |
| ProtectionStatusDetails | string |   |
| ProtectionStatusRank | int |   |
| Resource | string |   |
| ResourceGroup | string |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProvider | string |   |
| ResourceType | string |   |
| ScanDate | datetime |   |
| SignatureVersion | string |   |
| SourceComputerId | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubscriptionId | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| Threat | string |   |
| ThreatStatus | string |   |
| ThreatStatusDetails | string |   |
| ThreatStatusRank | int |   |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
| TypeofProtection | string |   |
| VMUUID | string |   |
