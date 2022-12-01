---
title: Azure Monitor Logs reference - ASimDnsActivityLogs
description: Reference for ASimDnsActivityLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
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
| DnsFlags | string | The DNS request flags, as provided by the reporting device.  The structure of the DNS flags information may vary between different reporting devices. |
| DnsFlagsAuthenticated | bool | The DNS authenticated answer flag, which is related to DNSSEC, indicates in a response that all data included in the answer and authority sections of the response have been verified by the server according to the policies of that server. see RFC 3655 Section 6.1 for more information. |
| DnsFlagsAuthoritative | bool | The DNS authoritative answer flag indicates whether the response from the server was authoritative. |
| DnsFlagsCheckingDisabled | bool | The DNS CD flag, which is related to DNSSEC, indicates in a query that non-verified data is acceptable to the system sending the query. |
| DnsFlagsRecursionAvailable | bool | The DNS RA flag indicates in a response that that server supports recursive queries. |
| DnsFlagsRecursionDesired | bool | The DNS recursion desired flag indicates in a request that that client would like the server to use recursive queries. |
| DnsFlagsTruncated | bool | The DNS TC flag indicates that a response was truncates as it exceeded the maximum response size. |
| DnsFlagsZ | bool | The DNS Z flag is a deprecated DNS flag, which might be reported by older DNS systems. |
| DnsNetworkDuration | int | The amount of time, in milliseconds, for the completion of DNS request. |
| DnsQuery | string | The domain that needs to be resolved. |
| DnsQueryClass | int | The DNS class ID as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryClassName | string | The DNS class name as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryType | int | The DNS resource record type codes as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsQueryTypeName | string | The DNS resource record type name as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsResponseCode | int | The DNS numerical response code as defined by the Internet Assigned Numbers Authority (IANA). |
| DnsResponseIpCountry | string | The country associated with the response IP address. |
| DnsResponseIpLatitude | real | The Latitude of the geographical coordinate associated with the response IP address. |
| DnsResponseIpLongitude | real | The longitude of the geographical coordinate associated with the response IP address. |
| DnsResponseName | string | The content of the response, as included in the record. The structure of the DNS response data may vary between different reporting devices. |
| DnsSessionId | string | The DNS session identifier as reported by the reporting device. |
| Dst | string | A unique identifier of the server that received the DNS request. |
| DstDeviceType | string | The type of the destination device. |
| DstDomain | string | The domain of the destination device. |
| DstDomainType | string | The type of DstDomain. |
| DstDvcId | string | The ID of the destination device. |
| DstDvcIdType | string | The type of DstDvcId. |
| DstFQDN | string | The destination device hostname, including domain information when available. |
| DstGeoCity | string | The city associated with the destination IP address. |
| DstGeoCountry | string | The country associated with the destination IP address. |
| DstGeoLatitude | real | The latitude of the geographical coordinate associated with the destination IP address. |
| DstGeoLongitude | real | The longitude of the geographical coordinate associated with the destination IP address. |
| DstGeoRegion | string | The region, or state, within a country, associated with the destination IP address. |
| DstHostname | string | The destination device hostname, excluding domain information. |
| DstIpAddr | string | The IP address of the server receiving the DNS request. For a regular DNS request, this value would typically be the reporting device, and in most cases set to 127.0.0.1. |
| DstPortNumber | int | Destination Port number. |
| Dvc | string | A unique identifier of the device reporting the event. The identifier can be either an IP Address, A hostname, or a device ID. |
| DvcAction | string | The action taken by the the reporting device on the request, such as blocking it. |
| DvcDomain | string | The domain of the device reporting the event. |
| DvcDomainType | string | The type of DvcDomain. Possible values include "Windows" and "FQDN". |
| DvcFQDN | string | The fully qualified hostname, including domain information, of the device reporting the event. |
| DvcHostname | string | The hostname of the device reporting the event. |
| DvcId | string | The unique ID of the device reporting the event. |
| DvcIdType | string | The type of DvcId. |
| DvcIpAddr | string | The IP Address of the device reporting the event. |
| DvcMacAddr | string | The MAC address of the device reporting the event. |
| DvcOs | string | The operating system running on the device reporting the event. |
| DvcOsVersion | string | The version of the operating system on the device reporting the event. |
| DvcZone | string | The network segment of the device reporting the event. |
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
| Src | string | A unique identifier of the source device. |
| SrcDeviceType | string | The type of the source device. |
| SrcDomain | string | The domain of the source device. |
| SrcDomainType | string | The type of SrcDomain. |
| SrcDvcId | string | The ID of the source device. |
| SrcDvcIdType | string | The type of SrcDvcId. |
| SrcFQDN | string | The source device hostname, including domain information. |
| SrcGeoCity | string | The city associated with the source IP address. |
| SrcGeoCountry | string | The country associated with the source IP address. |
| SrcGeoLatitude | real | The latitude of the geographical coordinate associated with the source IP address. |
| SrcGeoLongitude | real | The longitude of the geographical coordinate associated with the source IP address. |
| SrcGeoRegion | string | The region, or state, within a country, associated with the source IP address. |
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
| ThreatCategory | string | If a DNS event source also provides DNS security, it may also evaluate the DNS event. For example, it can search for the IP address or domain in a threat intelligence database, and assign the domain or IP address with a Threat Category. |
| ThreatConfidence | string | The confidence level of the threat identified, normalized to a value between 0 and a 100. |
| ThreatField | string | The field for which a threat was identified. The value is either SrcIpAddr, DstIpAddr, Domain, or DnsResponseName. |
| ThreatFirstReportedTime | string | The first time the IP address or domain were identified as a threat. |
| ThreatIpAddr | string | An IP address for which a threat was identified. The field ThreatField contains the name of the field ThreatIpAddr represents. If a threat is identified in the Domain field, this field should be empty. |
| ThreatIsActive | string | True ID the threat identified is considered an active threat. |
| ThreatLastReportedTime | string | The last time the IP address or domain were identified as a threat. |
| ThreatName | string | The name of the threat identified, as reported by the reporting device. |
| ThreatOriginalConfidence | string | The original confidence level of the threat identified, as reported by the reporting device. |
| ThreatOriginalRiskLevel | int | The original risk level associated with the threat identified, as reported by the reporting device. |
| ThreatRiskLevel | string | The risk level associated with the threat identified, normalized to a value between 0 and a 100. |
| TimeGenerated | datetime | The timestamp (UTC) reflecting the time in which the event was generated. |
| TransactionIdHex | string | The DNS unique hex transaction ID. |
| Type | string | The name of the table |
| UrlCategory | string | A DNS event source may also look up the category of the requested Domains. |
