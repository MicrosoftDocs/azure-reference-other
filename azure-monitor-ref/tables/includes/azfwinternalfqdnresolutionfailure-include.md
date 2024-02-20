---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AZFWInternalFqdnResolutionFailure
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Error | string | Description of the error that caused the failure of the FQDN resolution. |
| Fqdn | string | The FQDN which the firewall failed to resolve. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Policy | string | Name of the policy in which the rule with the failing FQDN resolution resides. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Rule | string | Name of the rule with the failing FQDN resolution. |
| RuleCollection | string | Name of the rule collection in which the rule with the failing FQDN resolution resides. |
| RuleCollectionGroup | string | Name of the rule collection group in which the rule with the failing FQDN resolution resides. |
| ServerIp | string | DNS Resolver server's IP address. |
| ServerPort | int | DNS Resolver server's port. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
