---
title: Azure Monitor Logs reference - ASimDnsActivityLogs
description: Reference for ASimDnsActivityLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 7/7/2022
---

# ASimDnsActivityLogs

 The ASim DNS activity schema represents DNS protocol activity, which may be logged either by a DNS server or by a device sending DNS requests to a DNS server. The DNS protocol activity includes DNS queries, DNS server updates, and DNS bulk data transfers. Since the schema represents protocol activity, it is governed by RFCs and officially assigned parameter lists. The DNS activity schema does not represent DNS server audit events.

## Categories

- Security
## Solutions

- Microsoft Sentinel
## Resource types

- Microsoft Sentinel DNS activity ASim schema




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalFields | dynamic | Additional information, represented using key/value pairs provided by the source which do not map to ASim. |
| DnsFlagsAuthenticated | bool | The DNS authenticated answer flag, which is related to DNSSEC, indicates in a response that all data included in the answer and authority sections of the response have been verified by the server according to the policies of that server. see RFC 3655 Section 6.1 for more information. |
| DnsFlagsAuthoritative | bool | The DNS authoritative answer flag indicates whether the response from the server was authoritative. |
| DnsFlagsCheckingDisabled | bool | The DNS CD flag, which is related to DNSSEC, indicates in a query that non-verified data is acceptable to the system sending the query. |
| DnsFlagsRecursionAvailable | bool | The DNS RA flag indicates in a response that that server supports recursive queries. |
| DnsFlagsRecursionDesired | bool | The DNS recursion desired flag indicates in a request that that client would like the server to use recursive queries. |
| DnsFlagsTruncates | bool | The DNS TC flag indicates that a response was truncates as it exceeded the maximum response size. |
| DnsFlagsZ | bool | The DNS Z flag is a deprecated DNS flag, which might be reported by older DNS systems. |
| DnsNetworkDuration | int | The amount of time, in milliseconds, for the completion of DNS request. |
| DnsQuery | string | The domain that needs to be resolved. |
| DnsQueryClass | int | The DNS class ID as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryClassName | string | The DNS class name as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryType | int | The DNS resource record type codes as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryTypeName | string | The DNS resource record type name as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsResponseCode | int | The DNS numerical response code as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsSessionId | string | The DNS session identifier as reported by the reporting device. |
| DstDeviceType | string | The type of the destination device. |
| DstDomain | string | The domain of the destination device. |
| DstDomainType | string | The type of DstDomain. |
| DstDvcId | string | The ID of the destination device. |
| DstDvcIdType | string | The type of DstDvcId. |
| DstFQDN | string | The destination device hostname, including domain information when available. |
| DstHostname | string | The destination device hostname, excluding domain information. |
| DstIpAddr | string | The IP address of the server receiving the DNS request. For a regular DNS request, this value would typically be the reporting device, and in most cases set to 127.0.0.1. |
| DstPortNumber | int | Destination Port number. |
| DvcAction | string | The action taken by the the reporting device on the request, such as blocking it. |
| DvcDomain | string | The domain of the device reporting the event. |
| DvcDomainType | string | The type of DvcDomain. Possible values include "Windows" and "FQDN". |
| DvcFQDN | string | The fully qualified hostname, including domain information, of the device reporting the event. |
| DvcHostname | string | The hostname of the device reporting the event. |
| DvcId | string | The unique ID of the device reporting the event. |
| DvcIdType | string | The type of DvcId. |
| DvcIpAddr | string | The IP Address of the device reporting the event. |
| DvcOs | string | The operating system running on the device reporting the event. |
| DvcOsVersion | string | The version of the operating system on the device reporting the event. |
| EventCount | int | The number of events described by the record. This value is used when the source supports aggregation, and a single record may represent multiple events. |
| EventMessage | string | A general message or description. |
| EventOriginalType | string | The original event type or ID, for example, the original Windows event ID. |
| EventOriginalUid | string | A unique ID of the original record. |
| EventProduct | string | The product generating the event. |
| EventReportUrl | string | A URL of a resource that provides additional information about the event. |
| EventResult | string | The outcome of the event, represented by one of the following values: Success, Partial, Failure, NA (Not Applicable). The value may not be provided directly by the sources, in which case it is derived from other event fields, for example, the EventResultDetails field. |
| EventResultDetails | string | The DNS response code as defined by the Internet Assigned Numbers Authority (IANA). |
| EventSubType | string | Either request or response. |
| EventType | string | Indicates the operation reported by the record. For DNS activity events, this value is the DNS opcode as defined by the Internet Assigned Numbers Authority (IANA). |
| EventVendor | string | The vendor of the product generating the event. |
| NetworkProtocol | string | The transport protocol used by the network resolution event. The value can be UDP or TCP. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| SrcDeviceType | string | The type of the source device. |
| SrcDomain | string | The domain of the source device. |
| SrcDomainType | string | The type of SrcDomain. |
| SrcDvcId | string | The ID of the source device. |
| SrcDvcIdType | string | The type of SrcDvcId. |
| SrcFQDN | string | The source device hostname, including domain information. |
| SrcHostname | string | The source device hostname, excluding domain information. |
| SrcIpAddr | string | The IP address of the client sending the DNS request. For a recursive DNS request, this value would typically be the reporting device, and in most cases, set to 127.0.0.1. |
| SrcOriginalUserType | string | The original source user type, as provided by the source. |
| SrcPortNumber | int | Source port of the DNS query. |
| SrcProcessGuid | string | A generated unique identifier (GUID) of the process that initiated the DNS request. |
| SrcProcessId | string | The process ID (PID) of the process that initiated the DNS request. |
| SrcProcessName | string | The name of the process that initiated the DNS request. |
| SrcUserId | string | A machine-readable, alphanumeric, unique representation of the source user. |
| SrcUserIdType | string | The type of the ID stored in the SrcUserId field. |
| SrcUsername | string | The Source username, including domain information when available. |
| SrcUsernameType | string | The type of the username stored in the SrcUsername field. |
| SrcUserType | string | The type of the source user. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| ThreatCategory | string | The threat category associated with the DNS event, if evaluated, for example by looking up the IP address or domain in a threat intelligence database. This value, when provided, is an enrichment and is not part of the DNS query itself. |
| TimeGenerated | datetime | The timestamp (UTC) reflecting the time in which the event was generated. |
| TransactionIdHex | string | The DNS unique hex transaction ID. |
| Type | string | The name of the table |
| UrlCategory | string | The category of the requested domain. This value, when provided, is an enrichment and is not part of the DNS query itself. |
