---
title: Azure Monitor Logs reference - AZFWInternalFqdnResolutionFailure
description: Reference for AZFWInternalFqdnResolutionFailure table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AZFWInternalFqdnResolutionFailure

 Contains all internal Firewall FQDN resolution requests that resulted in failure.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Error | string | Description of the error that caused the failure of the FQDN resolution. |
| Fqdn | string | The FQDN which the firewall failed to resolve. |
| _IsBillable | string |  |
| Policy | string | Name of the policy in which the rule with the failing FQDN resolution resides. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Rule | string | Name of the rule with the failing FQDN resolution. |
| RuleCollection | string | Name of the rule collection in which the rule with the failing FQDN resolution resides. |
| RuleCollectionGroup | string | Name of the rule collection group in which the rule with the failing FQDN resolution resides. |
| ServerIp | string | DNS Resolver server's IP address. |
| ServerPort | int | DNS Resolver server's port. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
