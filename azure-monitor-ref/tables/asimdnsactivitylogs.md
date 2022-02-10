---
title: Azure Monitor Logs reference - ASimDnsActivityLogs
description: Reference for ASimDnsActivityLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 2/10/2022
---

# ASimDnsActivityLogs

 The ASim DNS activity schema represents DNS protocol activity, which may be logged either by a DNS server or by a device sending DNS requests to a DNS server. The DNS protocol activity includes DNS queries, DNS server updates, and DNS bulk data transfers. Since the schema represents protocol activity, it is governed by RFCs and officially assigned parameter lists. The DNS activity schema does not represent DNS server audit events.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalFields | dynamic | Additional information, represented using key/value pairs provided by the source which do not map to ASim. |
| DnsFlagsAuthenticated | bool | The DNS authenticated answer flag, which is related to DNSSEC, indicates in a response that all data included in the answer and authority sections of the response have been verified by the server according to the policies of that server. see RFC 3655 Section 6.1 for more information. |
| DnsFlagsAuthoritative | bool | The DNS authoritative answer flag indicates whether the response from the server was authoritative. |
| DnsFlagsRecursionDesired | bool | The DNS recursion desired flag indicates in a request that that client would like the server to use recursive queries. |
| DnsNetworkDuration | int | The amount of time, in milliseconds, for the completion of DNS request. |
| DnsQuery | string | The domain that needs to be resolved. |
| DnsQueryClass | int | The DNS class ID as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryClassName | string | The DNS class name as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryType | int | The DNS resource record type codes as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryTypeName | string | The DNS resource record type name as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsResponseCode | int | The DNS numerical response code as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsSessionId | string | The DNS session identifier as reported by the reporting device. |
| DstIpAddr | string | The IP address of the server receiving the DNS request. For a regular DNS request, this value would typically be the reporting device, and in most cases set to 127.0.0.1. |
| DvcDomain | string | The domain of the device reporting the event. |
| DvcDomainType | string | The type of DvcDomain. Possible values include "Windows" and "FQDN". |
| DvcHostname | string | The hostname of the device reporting the event. |
| DvcIpAddr | string | The IP Address of the device reporting the event. |
| DvcOs | string | The operating system running on the device reporting the event. |
| DvcOsVersion | string | The version of the operating system on the device reporting the event. |
| EventCount | int | The number of events described by the record. This value is used when the source supports aggregation, and a single record may represent multiple events. |
| EventOriginalType | string | The original event type or ID, for example, the original Windows event ID. |
| EventProduct | string | The product generating the event. |
| EventResult | string | The outcome of the event, represented by one of the following values: Success, Partial, Failure, NA (Not Applicable). The value may not be provided directly by the sources, in which case it is derived from other event fields, for example, the EventResultDetails field. |
| EventResultDetails | string | The DNS response code as defined by the Internet Assigned Numbers Authority (IANA). |
| EventSubType | string | Either request or response. |
| EventType | string | Indicates the operation reported by the record. For DNS activity events, this value is the DNS opcode as defined by the Internet Assigned Numbers Authority (IANA). |
| EventVendor | string | The vendor of the product generating the event. |
| NetworkProtocol | string | The transport protocol used by the network resolution event. The value can be UDP or TCP. |
| SourceSystem | string |  |
| SrcIpAddr | string | The IP address of the client sending the DNS request. For a recursive DNS request, this value would typically be the reporting device, and in most cases, set to 127.0.0.1. |
| SrcPortNumber | int | Source port of the DNS query. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) reflecting the time in which the event was generated. |
| TransactionIdHex | string | The DNS unique hex transaction ID. |
| Type | string | The name of the table |
