---
title: Azure Monitor Logs reference - AZFWIdpsSignature
description: Reference for AZFWIdpsSignature table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AZFWIdpsSignature

 Contains all data plane packets that were matched with one or more IDPS signatures.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Action | string | Action taken by the firewall following the IDPS signature hit. |
| _BilledSize | real |  |
| Category | string | Category of the matched IDPS signature. |
| Description | string | Description of the matched IDPS signature. |
| DestinationIp | string | Packet's destination IP address. |
| DestinationPort | int | Packet's destination port. |
| _IsBillable | string |  |
| Protocol | string | Packet's network protocol. For example: UDP, TCP. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Severity | int | Severity of the matched IDPS signature. |
| SignatureId | string | ID of the matched IDPS signature. |
| SourceIp | string | Packet's source IP address. |
| SourcePort | int | Packet's source port. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
