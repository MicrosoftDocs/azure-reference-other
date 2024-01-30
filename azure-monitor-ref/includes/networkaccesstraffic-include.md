---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/29/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: NetworkAccessTraffic
---


| Column | Type | Description |
|---|---|---|
| Action | string | The action taken on the network session. Allowed, Denied. |
| AgentVersion | string | The version of the agent connecting. |
| _BilledSize | real | The record size in bytes |
| ConnectionId | string | Unique identifier representing the connection this traffic log was initiated from. |
| Description | string | Additional details describing the traffic. |
| DestinationFqdn | string | The destination device hostname, including domain information when available. |
| DestinationIp | string | The IP address of the connection or session destination. |
| DestinationPort | int | The destination IP port. |
| DestinationUrl | string | The Url link of the connection or session destination. |
| DestinationWebCategories | string | The destination FQDN's Web Categories. |
| DeviceCategory | string | Device type the transaction originated from. Client, Branch.  |
| DeviceId | string | The ID of the source device as reported in the record. |
| DeviceOperatingSystem | string | The client connecting operating system type. |
| DeviceOperatingSystemVersion | string | The client connecting operating system version. |
| FilteringProfileId | string | The ID of the Filtering Profile associated with the action performed on traffic. |
| FilteringProfileName | string | The name of the Filtering Profile associated with the action performed on traffic. |
| InitiatingProcessName | string | The process initiating the traffic transaction. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NetworkProtocol | string | The network protocol, IPv6 or IPv4. |
| OriginHeader | string | The origin header value. |
| PolicyId | string | The ID of the policy for which the request was denied by its rule. |
| PolicyName | string | The name of the filtering policy associated with the action performed on traffic. |
| PolicyRuleId | string | The ID of the rule for which the request was denied by. |
| ReceivedBytes | long | The number of bytes received. |
| ReferrerHeader | string | The Referer header value. |
| ResourceTenantId | string | Tenant ID that owns the resource. |
| RuleName | string | The name of the rule associated with the action performed on traffic. |
| SentBytes | long | The number of bytes sent. |
| SessionId | string | Unique identifier representing the session. |
| SourceIp | string | The IP address from which the connection or session originated. |
| SourcePort | int | The IP port from which the connection originated. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| ThreatType | string | The identified threat type associated with the traffic. |
| TimeGenerated | datetime | The date and time (UTC) that the event was generated. |
| TrafficType | string | The type of the target destination traffic. |
| TransactionId | string | Unique identifier that representing a roundtrip of request response. |
| TransportProtocol | string | The IP protocol used by the connection or session as listed in IANA protocol assignment. |
| Type | string | The name of the table |
| UserId | string | A machine-readable, alphanumeric, unique representation of the source user. |
| UserPrincipalName | string | The source username, including domain information when available. |
| XForwardedFor | string | X-Forwarded-For header of the HTTP request. |
