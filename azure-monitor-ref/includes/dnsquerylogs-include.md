---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/11/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: DNSQueryLogs
---


| Column | Type | Description |
|---|---|---|
| AdditionalRecords | dynamic | Array of additional resource records. |
| Answer | dynamic | Array of answers for DNS query. |
| Authority | dynamic | Array of authority DNS servers for DNS query. |
| _BilledSize | real | The record size in bytes |
| DestinationIpAddress | string | The IP address of the instance that the query was sent to (outbound endpoints). |
| DestinationPort | int | The port on the instance that the query was sent to. |
| DnsForwardingRulesetDomain | string | The domain which was hit in the DNS Forwarding ruleset. |
| DnsForwardingRulesetId | string | The ID of the DNS forwarding ruleset which was hit. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | Name of the operation. |
| PrivateResolverEndpointId | string | The ID of the resolver endpoint. Can be inbound, or outbound. |
| QueryClass | string | Specifies the protocol family. For example, IN for Internet. |
| QueryName | string | The domain name (contoso.com) or subdomain name (www.contoso.com) that was specified in the query. |
| QueryResponseTime | int | Response time for resolution of DNS query. |
| QueryType | string | Either the DNS record type that was specified in the request, or ANY. |
| Region | string | The region where the virtual network was created in. |
| ResolutionPath | string | Resolution path can be private zones, ruleset, or public DNS resolution. |
| ResolverPolicyDomainListId | string | The ID of the domain list which was hit. |
| ResolverPolicyId | string | The ID of the security policy which filtered the query. |
| ResolverPolicyRuleAction | string | Result after evaluation of the policy rules. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseCode | int | Response code that resolver returned in response to the DNS query. |
| SourceIpAddress | string | The IP address of the instance that the query originated from. |
| SourcePort | int | The port on the instance that the query originated from. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Transport | string | The protocol (UDP or TCP) used to submit the DNS query. |
| Type | string | The name of the table |
| Version | string | The version number of the query log format. |
| VirtualNetworkId | string | The ID of the virtual network that the query originated in. |
