---
title: Azure Monitor Logs reference - AZFWNatRuleAggregation
description: Reference for AZFWNatRuleAggregation table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# AZFWNatRuleAggregation

 Contains aggregated NAT Rule log data for Policy Analytics.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| NatRuleCount | int | Aggregated count of NAT rules. |
| Policy | string | Name of the policy in which the triggered rule resides. |
| Protocol | string | Packet's network protocol. For example: UDP, TCP. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Rule | string | Name of the triggered rule. |
| RuleCollection | string | Name of the rule collection in which the triggered rule resides. |
| RuleCollectionGroup | string | Name of the rule collection group in which the triggered rule resides. |
| SourceIp | string | Packet's source IP address. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| TranslatedIp | string | Original Destination IP address of the packet is replaced with TranslatedIp. |
| TranslatedPort | int | Original Destination port  of the packet is replaced with TranslatedPort. |
| Type | string | The name of the table |
