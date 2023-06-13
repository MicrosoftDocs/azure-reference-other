---
title: Azure Monitor Logs reference - AZFWFlowTrace
description: Reference for AZFWFlowTrace table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AZFWFlowTrace

 Flow logs across Azure Firewall instances. Log contains flow information, flags and the time period when the flows were recorded. Please follow the documentation to enable flow trace logging and details on how it is recorded.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Action | string | Action taken by the firewall to log additional flow information. |
| ActionReason | string | The reason for the action performed by the firewall. For example: when additional logging is enabled it shows `Additional TCP Log`. |
| _BilledSize | real |  |
| DestinationIp | string | Flow's destination IP address. |
| DestinationPort | int | Flow's destination port. |
| Flag | string | Flags set in the connection. For example: FIN, FIN-ACK, SYN-ACK, RST, INVALID. |
| _IsBillable | string |  |
| Protocol | string | Flow's network protocol. For example: UDP, TCP. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceIp | string | Flow's source IP address. |
| SourcePort | int | Flow's source port. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
