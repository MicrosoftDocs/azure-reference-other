---
title: Azure Monitor Logs reference - AZFWNetworkRule
description: Reference for AZFWNetworkRule table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AZFWNetworkRule

 Contains all Network Rule log data. Each match between data plane and network rule creates a log entry with the data plane packet and the matched rule's attributes.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Action | string | Action taken by the firewall following the match with this Network Rule. For example: Firewall may Allow/Deny this specific packet. |
| ActionReason | string | When no rule is triggered for a packet, this field contains the reason for the action performed by the firewall. For example: a packet dropped because no rule matched will show `Default Action`. |
| DestinationIp | string | Packet's destination IP address. |
| DestinationPort | int | Packet's destination port. |
| Policy | string | Name of the policy in which the triggered rule resides. |
| Protocol | string | Packet's network protocol. For example: UDP, TCP. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Rule | string | Name of the triggered rule. |
| RuleCollection | string | Name of the rule collection in which the triggered rule resides. |
| RuleCollectionGroup | string | Name of the rule collection group in which the triggered rule resides. |
| SourceIp | string | Packet's source IP address. |
| SourcePort | int | Packet's source port. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
