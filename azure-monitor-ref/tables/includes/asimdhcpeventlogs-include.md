---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ASimDhcpEventLogs
---


| Column | Type | Description |
|---|---|---|
| AdditionalFields | dynamic | Additional information, represented using key/value pairs provided by the source which do not map to ASim. |
| _BilledSize | real | The record size in bytes |
| DhcpCircuitId | string | The DHCP circuit ID, as defined by RFC3046. |
| DhcpLeaseDuration | int | The length of the lease granted to a client, in seconds. |
| DhcpSessionDuration | int | The amount of time, in milliseconds, for the completion of the DHCP session. |
| DhcpSessionId | string | The session identifier as reported by the reporting device. For the Windows DHCP server, set this to the TransactionID field. |
| DhcpSrcDHCId | string | The DHCP client ID, as defined by RFC4701. |
| DhcpSubscriberId | string | The DHCP subscriber ID, as defined by RFC3993. |
| DhcpUserClass | string | The DHCP User Class, as defined by RFC3004. |
| DhcpUserClassId | string | The DHCP User Class Id, as defined by RFC3004. |
| DhcpVendorClass | string | The DHCP Vendor Class, as defined by RFC3925. |
| DhcpVendorClassId | string | The DHCP Vendor Class Id, as defined by RFC3925. |
| DvcAction | string | For reporting security systems, the action taken by the system, if applicable. |
| DvcDescription | string | A descriptive text associated with the device. |
| DvcDomain | string | The domain of the device on which the event occurred or which reported the event, depending on the schema |
| DvcDomainType | string | The type of DvcDomain. |
| DvcFQDN | string | The hostname of the device on which the event occurred or which reported the event, depending on the schema. |
| DvcHostname | string | The hostname of the device on which the event occurred or which reported the event, depending on the schema. |
| DvcId | string | The unique ID of the device on which the event occurred or which reported the event, depending on the schema. |
| DvcIdType | string | The type of DvcId. |
| DvcInterface | string | The network interface on which data was captured. This field is typically relevant to network related activity which is captured by an intermediate or tap device. |
| DvcIpAddr | string | The IP address of the device on which the event occurred or which reported the event, depending on the schema. |
| DvcMacAddr | string | The MAC address of the device on which the event occurred or which reported the event. |
| DvcOriginalAction | string | The original DvcAction as provided by the reporting device. |
| DvcOs | string | The operating system running on the device on which the event occurred or which reported the event. |
| DvcOsVersion | string | The version of the operating system on the device on which the event occurred or which reported the event. |
| DvcScope | string | The cloud platform scope the device belongs to. DvcScope map to a subscription name on Azure and to an account ID on AWS. |
| DvcScopeId | string | The cloud platform scope ID the device belongs to. DvcScopeId map to a subscription ID on Azure and to an account ID on AWS. |
| DvcZone | string | The network on which the event occurred or which reported the event, depending on the schema. The zone is defined by the reporting device. |
| EventCount | int | The number of events described by the record. This value is used when the source supports aggregation, and a single record might represent multiple events. |
| EventEndTime | datetime | The time in which the event ended. If the source supports aggregation and the record represents multiple events, the time when the last event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventMessage | string | A general message or description, either included in or generated from the record. |
| EventOriginalResultDetails | string | The original result details provided by the source. This value is used to derive EventResultDetails, which should have only one of the values documented for each schema. |
| EventOriginalSeverity | string | The original severity as provided by the reporting device. This value is used to derive EventSeverity. |
| EventOriginalSubType | string | The original event subtype or ID, if provided by the source. |
| EventOriginalType | string | The original event type or ID, if provided by the source. |
| EventOriginalUid | string | A unique ID of the original record, if provided by the source. |
| EventOwner | string | The owner of the event, which is usually the department or subsidiary in which it was generated. |
| EventProduct | string | The product generating the event. The value should be one of the values listed in Vendors and Products. |
| EventProductVersion | string | The version of the product generating the event. |
| EventReportUrl | string | A URL provided in the event for a resource that provides more information about the event. |
| EventResult | string | The outcome of the event, represented by one of the following values: Success, Partial, Failure, NA (Not Applicable). |
| EventResultDetails | string | Reason or details for the result reported in the EventResult field. |
| EventSchema | string | The schema the event is normalized to. Each schema documents its schema name. |
| EventSchemaVersion | string | The version of the schema. Each schema documents its current version. |
| EventSeverity | string | The severity of the event. |
| EventStartTime | datetime | The time in which the event started. If the source supports aggregation and the record represents multiple events, the time when the first event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventSubType | string | Describes a subdivision of the operation reported in the EventType field. |
| EventType | string | Describes the operation reported by the record. |
| EventVendor | string | The vendor of the product generating the event. The value should be one of the values listed in Vendors and Products. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| RequestedIpAddr | string | The IP address requested by the DHCP client, when available. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RuleName | string | The name or ID of the rule by associated with the inspection results. |
| RuleNumber | int | The number of the rule associated with the inspection results. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SrcDescription | string | A descriptive text associated with the device. |
| SrcDeviceType | string | The type of the device. |
| SrcDomain | string | The domain of the device. |
| SrcDomainType | string | The type of the domain. |
| SrcDvcId | string | The ID of the device. |
| SrcDvcIdType | string | The type of the DvcId. |
| SrcDvcScope | string | The cloud platform scope the device belongs to. |
| SrcDvcScopeId | string | The cloud platform scope ID the device belongs to. |
| SrcFQDN | string | The device hostname, including domain information when available. |
| SrcGeoCity | string | The city associated with the source IP address. |
| SrcGeoCountry | string | The country associated with the source IP address. |
| SrcGeoLatitude | real | The latitude of the geographical coordinate associated with the source IP address. |
| SrcGeoLongitude | real | The longitude of the geographical coordinate associated with the source IP address. |
| SrcGeoRegion | string | The region within a country associated with the source IP address.. |
| SrcHostname | string | The device hostname, excluding domain information. |
| SrcIpAddr | string | The IP address of the source device. |
| SrcMacAddr | string | The MAC address of the network interface from which the connection or session originated. |
| SrcOriginalRiskLevel | string | The risk level associaeted with the identified Source as reported by the reporting device. |
| SrcOriginalUserType | string | The original source user type, if provided by the source. |
| SrcPortNumber | int | The IP port on which the device communicated, if applicable. |
| SrcRiskLevel | int | The risk level associated with the identified Source. |
| SrcUserId | string | A machine-readable, alphanumeric, unique representation of the user. |
| SrcUserIdType | string | The type of SrcUserId. |
| SrcUsername | string | The user's username, including domain information when available. |
| SrcUsernameType | string | The type of username. |
| SrcUserScope | string | The type of username. |
| SrcUserScopeId | string | The scope ID, such as Azure AD tenant ID, in which UserId and Username are defined. |
| SrcUserSessionId | string | The unique ID of the sign-in session of the user. |
| SrcUserType | string | The type of user |
| SrcUserUid | string | The Unix or Linux user ID of the user. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| ThreatCategory | string | The category of the threat or malware identified in activity. |
| ThreatConfidence | int | The confidence level of the threat identified, normalized to a value between 0 and a 100. |
| ThreatField | string | The field for which a threat was identified. |
| ThreatFirstReportedTime | datetime | The first time the IP address or domain were identified as a threat. |
| ThreatId | string | The ID of the threat or malware identified in the activity. |
| ThreatIsActive | bool | True ID the threat identified is considered an active threat. |
| ThreatLastReportedTime | datetime | The last time the IP address or domain were identified as a threat. |
| ThreatName | string | The name of the threat or malware identified in the activity. |
| ThreatOriginalConfidence | string | The original confidence level of the threat identified, as reported by the reporting device. |
| ThreatOriginalRiskLevel | string | The risk level as reported by the reporting device. |
| ThreatRiskLevel | int | The risk level associated with the identified threat. The level should be a number between 0 and 100. |
| TimeGenerated | datetime | The timestamp (UTC) reflecting the time in which the event was generated. |
| Type | string | The name of the table |
