---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ASimDnsActivityLogs
---


| Column | Type | Description |
|---|---|---|
| AdditionalFields | dynamic | Additional information, represented using key/value pairs provided by the source which do not map to ASim. |
| _BilledSize | real | The record size in bytes |
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
| DnsResponseIpCity | string | The city associated with the response IP address. |
| DnsResponseIpCountry | string | The country associated with the response IP address. |
| DnsResponseIpLatitude | real | The Latitude of the geographical coordinate associated with the response IP address. |
| DnsResponseIpLongitude | real | The longitude of the geographical coordinate associated with the response IP address. |
| DnsResponseIpRegion | string | The region, or state, within a country, associated with the source IP address. |
| DnsResponseName | string | The content of the response, as included in the record. The structure of the DNS response data may vary between different reporting devices. |
| DnsSessionId | string | The DNS session identifier as reported by the reporting device. |
| Dst | string | A unique identifier of the server that received the DNS request. |
| DstDescription | string | A descriptive text associated with the destination. |
| DstDeviceType | string | The type of the destination device. |
| DstDomain | string | The domain of the destination device. |
| DstDomainType | string | The type of DstDomain. |
| DstDvcId | string | The ID of the destination device. |
| DstDvcIdType | string | The type of DstDvcId. |
| DstDvcScope | string | The cloud platform scope the destination device belongs to. DvcScope maps to a subscription on Azure and to an account on AWS. |
| DstDvcScopeId | string | The cloud platform scope ID the destination device belongs to. DvcScopeId map to a subscription ID on Azure and to an account ID on AWS. |
| DstFQDN | string | The destination device hostname, including domain information when available. |
| DstGeoCity | string | The city associated with the destination IP address. |
| DstGeoCountry | string | The country associated with the destination IP address. |
| DstGeoLatitude | real | The latitude of the geographical coordinate associated with the destination IP address. |
| DstGeoLongitude | real | The longitude of the geographical coordinate associated with the destination IP address. |
| DstGeoRegion | string | The region, or state, within a country, associated with the destination IP address. |
| DstHostname | string | The destination device hostname, excluding domain information. |
| DstIpAddr | string | The IP address of the server receiving the DNS request. For a regular DNS request, this value would typically be the reporting device, and in most cases set to 127.0.0.1. |
| DstOriginalRiskLevel | string | The risk level associated with the destination device as reported by the reporting device. |
| DstPortNumber | int | Destination Port number. |
| DstRiskLevel | int | The risk level associated with the destination device. |
| Dvc | string | A unique identifier of the device reporting the event. The identifier can be either an IP Address, A hostname, or a device ID. |
| DvcAction | string | The action taken by the the reporting device on the request, such as blocking it. |
| DvcDescription | string | A descriptive text associated with the device. For example: Primary Domain Controller. |
| DvcDomain | string | The domain of the device reporting the event. |
| DvcDomainType | string | The type of DvcDomain. Possible values include "Windows" and "FQDN". |
| DvcFQDN | string | The fully qualified hostname, including domain information, of the device reporting the event. |
| DvcHostname | string | The hostname of the device reporting the event. |
| DvcId | string | The unique ID of the device reporting the event. |
| DvcIdType | string | The type of DvcId. |
| DvcInterface | string | The network interface on which data was captured. This field is typically relevant to network related activity which is captured by an intermediate or tap device. |
| DvcIpAddr | string | The IP Address of the device reporting the event. |
| DvcMacAddr | string | The MAC address of the device reporting the event. |
| DvcOriginalAction | string | The original DvcAction as provided by the reporting device. |
| DvcOs | string | The operating system running on the device reporting the event. |
| DvcOsVersion | string | The version of the operating system on the device reporting the event. |
| DvcScope | string | The cloud platform scope the device belongs to. DvcScope map to a subscription ID on Azure and to an account ID on AWS. |
| DvcScopeId | string | The cloud platform scope ID the device belongs to. DvcScopeId map to a subscription ID on Azure and to an account ID on AWS. |
| DvcZone | string | The network segment of the device reporting the event. |
| EventCount | int | The number of events described by the record. This value is used when the source supports aggregation, and a single record may represent multiple events. |
| EventEndTime | datetime | The time at which the event ended. If the source supports aggregation and the record represents multiple events, the time that the last event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventMessage | string | A general message or description. |
| EventOriginalSeverity | string | The original severity as provided by the reporting device. This value is used to derive EventSeverity. |
| EventOriginalType | string | The original event type or ID, for example, the original Windows event ID. |
| EventOriginalUid | string | A unique ID of the original record. |
| EventOwner | string | The owner of the event, which is usually the department or subsidiary in which it was generated. |
| EventProduct | string | The product generating the event. |
| EventProductVersion | string | The version of the product generating the event. |
| EventReportUrl | string | A URL of a resource that provides additional information about the event. |
| EventResult | string | The outcome of the event, represented by one of the following values: Success, Partial, Failure, NA (Not Applicable). The value may not be provided directly by the sources, in which case it is derived from other event fields, for example, the EventResultDetails field. |
| EventResultDetails | string | The DNS response code as defined by the Internet Assigned Numbers Authority (IANA). |
| EventSchemaVersion | string | The version of the schema. |
| EventSeverity | string | The severity of the event. Valid values are: Informational, Low, Medium, or High. |
| EventStartTime | datetime | The time at which the event started. If the source supports aggregation and the record represents multiple events, the time that the first event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventSubType | string | Either request or response. |
| EventType | string | Indicates the operation reported by the record. For DNS activity events, this value is the DNS opcode as defined by the Internet Assigned Numbers Authority (IANA). |
| EventVendor | string | The vendor of the product generating the event. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NetworkProtocol | string | The transport protocol used by the network resolution event. The value can be UDP or TCP. |
| NetworkProtocolVersion | string | The version of the network protocol. Typically used to differentiate between IPv4 and Ipv6. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RuleName | string | The name or ID of the rule by associated with the inspection results. |
| RuleNumber | int | The number of the rule associated with the inspection results. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Src | string | A unique identifier of the source device. |
| SrcDescription | string | The number of the rule associated with the inspection results. |
| SrcDeviceType | string | The type of the source device. |
| SrcDomain | string | The domain of the source device. |
| SrcDomainType | string | The type of SrcDomain. |
| SrcDvcId | string | The ID of the source device. |
| SrcDvcIdType | string | The type of SrcDvcId. |
| SrcDvcScope | string | The cloud platform scope the source device belongs to. DvcScope maps to a subscription on Azure and to an account on AWS. |
| SrcDvcScopeId | string | The cloud platform scope ID the source device belongs to. DvcScopeId map to a subscription ID on Azure and to an account ID on AWS. |
| SrcFQDN | string | The source device hostname, including domain information. |
| SrcGeoCity | string | The city associated with the source IP address. |
| SrcGeoCountry | string | The country associated with the source IP address. |
| SrcGeoLatitude | real | The latitude of the geographical coordinate associated with the source IP address. |
| SrcGeoLongitude | real | The longitude of the geographical coordinate associated with the source IP address. |
| SrcGeoRegion | string | The region, or state, within a country, associated with the source IP address. |
| SrcHostname | string | The source device hostname, excluding domain information. |
| SrcIpAddr | string | The IP address of the client sending the DNS request. For a recursive DNS request, this value would typically be the reporting device, and in most cases, set to 127.0.0.1. |
| SrcOriginalRiskLevel | string | The risk level associated with the source device as reported by the reporting device. |
| SrcOriginalUserType | string | The original source user type, as provided by the source. |
| SrcPortNumber | int | Source port of the DNS query. |
| SrcProcessGuid | string | A generated unique identifier (GUID) of the process that initiated the DNS request. |
| SrcProcessId | string | The process ID (PID) of the process that initiated the DNS request. |
| SrcProcessName | string | The name of the process that initiated the DNS request. |
| SrcRiskLevel | int | The risk level associated with the source device. |
| SrcUserId | string | A machine-readable, alphanumeric, unique representation of the source user. |
| SrcUserIdType | string | The type of the ID stored in the SrcUserId field. |
| SrcUsername | string | The Source username, including domain information when available. |
| SrcUsernameType | string | The type of the username stored in the SrcUsername field. |
| SrcUserScope | string | The scope, such as Azure AD tenant, in which SrcUserId and SrcUsername are defined. |
| SrcUserScopeId | string | The ID of the scope, such as Azure AD tenant, in which SrcUserId and SrcUsername are defined. |
| SrcUserSessionId | string | The unique ID of the sign-in session of the source user. |
| SrcUserType | string | The type of the source user. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| ThreatCategory | string | If a DNS event source also provides DNS security, it may also evaluate the DNS event. For example, it can search for the IP address or domain in a threat intelligence database, and assign the domain or IP address with a Threat Category. |
| ThreatConfidence | int | The confidence level of the threat identified, normalized to a value between 0 and a 100. |
| ThreatField | string | The field for which a threat was identified. The value is either SrcIpAddr, DstIpAddr, Domain, or DnsResponseName. |
| ThreatFirstReportedTime | string | The first time the IP address or domain were identified as a threat. |
| ThreatFirstReportedTime_d | datetime | The first time the IP address or domain were identified as a threat. |
| ThreatId | string | The ID of the threat or malware identified in the web session. |
| ThreatIpAddr | string | An IP address for which a threat was identified. The field ThreatField contains the name of the field ThreatIpAddr represents. If a threat is identified in the Domain field, this field should be empty. |
| ThreatIsActive | bool | True ID the threat identified is considered an active threat. |
| ThreatLastReportedTime | string | The last time the IP address or domain were identified as a threat. |
| ThreatLastReportedTime_d | datetime | The last time the IP address or domain were identified as a threat. |
| ThreatName | string | The name of the threat identified, as reported by the reporting device. |
| ThreatOriginalConfidence | string | The original confidence level of the threat identified, as reported by the reporting device. |
| ThreatOriginalRiskLevel | int | The original risk level associated with the threat identified, as reported by the reporting device. |
| ThreatOriginalRiskLevel_s | string | The risk level associated with the threat identified, normalized to a value between 0 and a 100. |
| ThreatRiskLevel | int | The risk level associated with the threat identified, normalized to a value between 0 and a 100. |
| TimeGenerated | datetime | The timestamp (UTC) reflecting the time in which the event was generated. |
| TransactionIdHex | string | The DNS unique hex transaction ID. |
| Type | string | The name of the table |
| UrlCategory | string | A DNS event source may also look up the category of the requested Domains. |
