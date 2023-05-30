---
title: Azure Monitor Logs reference - NetworkAccessTraffic
description: Reference for NetworkAccessTraffic table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/26/2023
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
| Action | string | The action taken on the network session. Allowed, Denied. |
| AgentVersion | string | The version of the agent connecting. |
| AppliedRuleId | string | The ID of the rule for which the request was denied by. |
| _BilledSize | real |  |
| ConnectionId | string | Unique identifier representing the connection this traffic log was initiated from. |
| CreationTime | datetime | The date and time (UTC) that the network connection was created. |
| DestinationFQDN | string | The destination device hostname, including domain information when available. |
| DestinationIp | string | The IP address of the connection or session destination. |
| DestinationPort | string | The destination IP port. |
| DeviceCategory | string | Device type the transaction originated from. Client, Branch.  |
| DeviceId | string | The ID of the source device as reported in the record. |
| DeviceOperatingSystem | string | The client connecting operating system type. |
| DeviceOperatingSystemVersion | string | The client connecting operating system version. |
| _IsBillable | string |  |
| NetworkProtocol | string | The network protocol, IPv6 \ IPv4. |
| OriginHeader | string | The Origin header value. |
| PolicyId | string | The ID of the policy for which the request was denied by its rule. |
| ReceivedBytes | long | The number of bytes received. |
| ReferrerHeader | string | The Referer header value. |
| SentBytes | long | The number of bytes sent. |
| SessionId | string | Unique identifier representing the session. |
| SourceIp | string | The IP address from which the connection or session originated. |
| SourcePort | string | The IP port from which the connection originated. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time (UTC) that the event was generated. |
| TrafficType | string | The type of the target destination traffic. |
| TransactionId | string | Unique identifier that representing a roundtrip of request response. |
| TransportProtocol | string | The IP protocol used by the connection or session as listed in IANA protocol assignment. |
| Type | string | The name of the table |
| UserId | string | A machine-readable, alphanumeric, unique representation of the source user. |
| UserPrincipalName | string | The source username, including domain information when available. |
| XForwardedFor | string | X-Forwarded-For header of the HTTP request. |
