---
title: Azure Monitor Logs reference - AZFWThreatIntel
description: Reference for AZFWThreatIntel table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AZFWThreatIntel

 Contains all Threat Intelligence events.

## Categories

- Security
## Solutions

- LogManagement
## Resource types

- Firewalls




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Action | string | Action taken by the firewall following the Threat Intelligence hit. |
| DestinationIp | string | Packet's destination IP address. |
| DestinationPort | int | Packet's destination port. |
| Fqdn | string | Request's target address in FQDN (Fully qualified Domain Name). For example: www.microsoft.com. |
| IsTlsInspected | bool | True if connection is TLS inspected. False otherwise. |
| Protocol | string | Packet's network protocol. For example: UDP, TCP. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceIp | string | Packet's source IP address. |
| SourcePort | int | Packet's source port. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetUrl | string | Request's target address URL. Available only for HTTP or TLS-inspected HTTPS requests. For example: https://www.microsoft.com/en-us/about. |
| TenantId | string |  |
| ThreatDescription | string | Description of the Threat that was identified by the firewall. |
| TimeGenerated | datetime | Timestamp (UTC) when the data plane log was created. |
| Type | string | The name of the table |
