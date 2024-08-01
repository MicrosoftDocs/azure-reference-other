---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AZFWApplicationRuleAggregation
---


| Column | Type | Description |
|---|---|---|
| Action | string | Action taken by the firewall following the Application rule hit. |
| ActionReason | string | When no rule is triggered for a packet, this field contains the reason for the action performed by the firewall. |
| ApplicationRuleCount | int | Aggregated count of Application rule. |
| _BilledSize | real | The record size in bytes |
| DestinationPort | int | Request's destination port. |
| Fqdn | string | Request's target address in FQDN (Fully qualified Domain Name). For example: www.microsoft.com. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Policy | string | Name of the policy in which the triggered rule resides. |
| Protocol | string | Request's network protocol. For example: HTTP/HTTPS. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Rule | string | Name of the triggered rule. |
| RuleCollection | string | Name of the rule collection in which the triggered rule resides. |
| RuleCollectionGroup | string | Name of the rule collection group in which the triggered rule resides. |
| SourceIp | string | Request's source IP address. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetUrl | string | Request's target address URL. Available only for HTTP or TLS-inspected HTTPS requests. For example: https://www.microsoft.com/en-us/about. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
