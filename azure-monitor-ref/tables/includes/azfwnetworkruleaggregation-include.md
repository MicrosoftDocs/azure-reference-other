---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AZFWNetworkRuleAggregation
---


| Column | Type | Description |
|---|---|---|
| Action | string | Action taken by the firewall following the match with this Network rule. For example: Firewall may Allow/Deny this specific session/packet. |
| ActionReason | string | When no rule is triggered for a request, this field contains the reason for the action performed by the firewall. For example: a packet dropped because no rule matched will show `Default Action`. |
| _BilledSize | real | The record size in bytes |
| DestinationIp | string | Packet's destination IP address. |
| DestinationPort | int | Packet's destination port. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsDefaultRule | bool | True if no network rule was hit. False otherwise. |
| NetworkRuleCount | int | Aggregated count of network rule. |
| Policy | string | Name of the policy in which the triggered rule resides. |
| Protocol | string | Packet's network protocol. For example: UDP, TCP. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Rule | string | Name of the triggered rule. |
| RuleCollection | string | Name of the rule collection in which the triggered rule resides. |
| RuleCollectionGroup | string | Name of the rule collection group in which the triggered rule resides. |
| SourceIp | string | Packet's source IP address. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
