---
title: Azure Monitor Logs reference - AZFWApplicationRule
description: Reference for AZFWApplicationRule table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# AZFWApplicationRule

 Contains all Application rule log data. Each match between data plane and Application rule creates a log entry with the data plane packet and the matched rule's attributes.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Action | string | Action taken by the firewall following the Application rule hit. |
| ActionReason | string | When no rule is triggered for a request, this field contains the reason for the action performed by the firewall. For example: a packet dropped because no rule matched will show `Default Action`. |
| DestinationPort | int | Request's destination port. |
| Fqdn | string | Request's target address in FQDN (Fully qualified Domain Name). For example: www.microsoft.com. |
| IsTlsInspected | bool | True if the connection is TLS inspected. False otherwise. |
| Policy | string | Name of the policy in which the triggered rule resides. |
| Protocol | string | Request's network protocol. For example: HTTP, HTTPS. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Rule | string | Name of the triggered rule. |
| RuleCollection | string | Name of the rule collection in which the triggered rule resides. |
| RuleCollectionGroup | string | Name of the rule collection group in which the triggered rule resides. |
| SourceIp | string | Request's source IP address. |
| SourcePort | int | Request's source port. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetUrl | string | Request's target address URL. Available only for HTTP or TLS-inspected HTTPS requests. For example: https://www.microsoft.com/en-us/about. |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
| WebCategory | string | Web Category identified for the requested FQDN (Azure Firewall Standard) or URL (Azure Firewall Premium). If a web category is not available for this request, the field is empty. |
