---
title: Azure Monitor Logs reference - NetworkAccessTraffic
description: Reference for NetworkAccessTraffic table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/23/2023
---

# NetworkAccessTraffic

 This table is part of Identity and Network Access, which contains Network Traffic Access logs. These logs can be leveraged for policy, risk, and traffic management, as well as to monitor users experience.

## Categories

- Security
- Network
- IT & Management Tools
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AgentVersion | string | The version of the agent connecting. |
| CorrelationId | string | ID to provide connection trail. |
| DestinationFQDN | string | The destination device hostname, including domain information when available. |
| DestinationIp | string | The IP address of the connection or session destination. |
| DestinationPort | int | The destination IP port. |
| DeviceId | string | The ID of the source device as reported in the record. |
| DeviceOperatingSystem | string | The client connecting operating system type. |
| DeviceOperatingSystemVersion | string | The client connecting operating system version. |
| NetworkProtocol | string | The IP protocol used by the connection or session as listed in IANA protocol assignment. |
| SourceIp | string | The IP address from which the connection or session originated. |
| SourcePort | int | The IP port from which the connection originated. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time (UTC) that the event arrived. |
| TimeStamp | datetime | The date and time (UTC) that the connection was created. |
| TrafficType | string | The type of the target destination. Internet Access, Private Access, M365. |
| Type | string | The name of the table |
| UserId | string | A machine-readable, alphanumeric, unique representation of the source user. |
| UserPrincipalName | string | The source username, including domain information when available. |
