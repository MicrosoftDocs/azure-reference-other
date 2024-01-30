---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/29/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ASimFileEventLogs
---


| Column | Type | Description |
|---|---|---|
| ActingProcessCommandLine | string | The command line used to run the acting process. |
| ActingProcessGuid | string | A generated unique identifier (GUID) of the acting process. |
| ActingProcessId | string | The process ID (PID) of the acting process. |
| ActingProcessName | string | The name of the acting process. |
| ActorOriginalUserType | string | The original actor user type as provided by the reporting device. |
| ActorScope | string | The scope, such as Azure AD tenant, in which ActorUserId and ActorUsername are defined. |
| ActorScopeId | string | The scope ID, such as Azure AD Directory ID, in which ActorUserId and ActorUsername are defined. |
| ActorSessionId | string | The unique ID of the login session of the Actor. |
| ActorUserAadId | string | The Azure Active Directory ID of the actor. |
| ActorUserId | string | A machine-readable, alphanumeric, unique representation of the actor. |
| ActorUserIdType | string | The type of the ID stored in the ActorUserId field. |
| ActorUsername | string | The Actor username, including domain information when available. |
| ActorUsernameType | string | Specifies the type of the user name stored in the ActorUsername field. |
| ActorUserSid | string | The Windows user ID (SIDs) of the actor. |
| ActorUserType | string | The type of actor. |
| AdditionalFields | dynamic | Additional information, represented using key/value pairs provided by the source which do not map to ASim. |
| _BilledSize | real | The record size in bytes |
| DvcAction | string | The action taken on the web session. |
| DvcDescription | string | A descriptive text associated with the device. |
| DvcDomain | string | The domain of the device reporting the event. |
| DvcDomainType | string | The type of DvcDomain. Valid values include 'Windows' and 'FQDN'. |
| DvcFQDN | string | The hostname of the device on which the event occurred or which reported the event. |
| DvcHostname | string | The hostname of the device reporting the event. |
| DvcId | string | The unique ID of the device on which the event occurred or which reported the event. |
| DvcIdType | string | The type of DvcId. |
| DvcInterface | string | The original DvcAction as provided by the reporting device. |
| DvcIpAddr | string | The IP address of the device reporting the event. |
| DvcMacAddr | string | The MAC address of the device on which the event occurred or which reported the event. |
| DvcOriginalAction | string | The original DvcAction as provided by the reporting device. |
| DvcOs | string | The operating system running on the device on which the event occurred or which reported the event. |
| DvcOsVersion | string | The version of the operating system on the device on which the event occurred or which reported the event. |
| DvcScope | string | The cloud platform scope the device belongs to. DvcScope map to a subscription name on Azure and to an account ID on AWS. |
| DvcScopeId | string | The cloud platform scope ID the device belongs to. DvcScopeId map to a subscription ID on Azure and to an account ID on AWS. |
| DvcZone | string | The network on which the event occurred or which reported the event, depending on the schema. |
| EventCount | int | This value is used when the source supports aggregation, and a single record may represent multiple events. |
| EventEndTime | datetime | The time in which the event ended. If the source supports aggregation and the record represents multiple events, the time that the last event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventMessage | string | A general message or description. |
| EventOriginalResultDetails | string | The original result details provided by the source. This value is used to derive EventResultDetails, which should have only one of the values documented for each schema. |
| EventOriginalSeverity | string | The original severity as provided by the reporting device. This value is used to derive EventSeverity. |
| EventOriginalSubType | string | The original event subtype or ID, if provided by the source. For example, this field will be used to store the original Windows logon type. This value is used to derive EventSubType, which should have only one of the values documented for each schema. |
| EventOriginalType | string | The original event type or ID, if provided by the source. |
| EventOriginalUid | string | A unique ID of the original record, if provided by the source. |
| EventOwner | string | The owner of the event, which is usually the department or subsidiary in which it was generated. |
| EventProduct | string | The product generating the event. |
| EventProductVersion | string | The version of the product generating the event. |
| EventReportUrl | string | A URL provided in the event for a resource that provides more information about the event. |
| EventResult | string | The outcome of the event, represented by one of the following values: Success, Partial, Failure, NA (Not Applicable). The value may not be provided directly by the sources, in which case it is derived from other event fields, for example, the EventResultDetails field. |
| EventResultDetails | string | The HTTP status code. |
| EventSchema | string | The schema the event is normalized to. Each schema documents its schema name. |
| EventSchemaVersion | string | The version of the schema. |
| EventSeverity | string | The severity of the event. Valid values are: Informational, Low, Medium, or High. |
| EventStartTime | datetime | The time in which the event started. If the source supports aggregation and the record represents multiple events, the time that the first event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventSubType | string | Additional description of the event type, if applicable. |
| EventType | string | The operation reported by the record. |
| EventVendor | string | The vendor of the product generating the event. |
| HashType | string | The type of hash stored in the Hash alias field. |
| HttpUserAgent | string | When the operation is initiated using HTTP or HTTPS, the HTTP user agent header. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NetworkApplicationProtocol | string | When the operation is initiated by a remote system, the application layer protocol used by the connection or session. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RuleName | string | The name or ID of the rule by associated with the inspection results. |
| RuleNumber | int | The number of the rule associated with the inspection results. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SrcDescription | string | A descriptive text associated with the device. |
| SrcDeviceType | string | The type of the source device.  |
| SrcDomain | string | The domain of the source device. |
| SrcDomainType | string | The type of SrcDomain. |
| SrcDvcId | string | The ID of the source device. |
| SrcDvcIdType | string | The type of SrcDvcId. |
| SrcDvcScope | string | The cloud platform scope the device belongs to.  |
| SrcDvcScopeId | string | The cloud platform scope ID the device belongs to. |
| SrcFileCreationTime | datetime | The time at which the source file was created. |
| SrcFileDirectory | string | The source file folder or location. |
| SrcFileExtension | string | The source file extension. |
| SrcFileMD5 | string | The MD5 hash of the source file. |
| SrcFileMimeType | string | The Mime or Media type of the source file. |
| SrcFileName | string | The name of the source file, without a path or a location, but with an extension if relevant. |
| SrcFilePath | string | The full, normalized path of the source file, including the folder or location, the file name, and the extension. |
| SrcFilePathType | string | The type of SrcFilePath. |
| SrcFileSHA1 | string | The SHA-1 hash of the source file. |
| SrcFileSHA256 | string | The SHA-256 hash of the source file. |
| SrcFileSHA512 | string | The SHA-512 hash of the source file. |
| SrcFileSize | long | The size of the source file in bytes. |
| SrcFQDN | string | The source device hostname, including domain information when available. |
| SrcGeoCity | string | The city associated with the source IP address. |
| SrcGeoCountry | string | The country associated with the source IP address. |
| SrcGeoLatitude | real | The latitude of the geographical coordinate associated with the source IP address. |
| SrcGeoLongitude | real | The longitude of the geographical coordinate associated with the source IP address. |
| SrcGeoRegion | string | The region within a country associated with the source IP address. |
| SrcHostname | string | The source device hostname, excluding domain information. If no device name is available, store the relevant IP address in this field. |
| SrcIpAddr | string | When the operation is initiated by a remote system, the IP address of this system. |
| SrcMacAddr | string | The MAC address of the source device. |
| SrcOriginalRiskLevel | string | The risk level associated with the source. As reported by the reporting device or enriched. |
| SrcPortNumber | int | When the operation is initiated by a remote system, the port number from which the connection was initiated. |
| SrcRiskLevel | int | The risk level associated with the source. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetAppId | string | The ID of the destination application, as reported by the reporting device. |
| TargetAppName | string | The name of the destination application. |
| TargetAppType | string | The type of the destination application. |
| TargetFileCreationTime | datetime | The time at which the target file was created. |
| TargetFileDirectory | string | The target file folder or location. |
| TargetFileExtension | string | The target file extension. |
| TargetFileMD5 | string | The MD5 hash of the target file. |
| TargetFileMimeType | string | The Mime or Media type of the target file. |
| TargetFileName | string | The name of the target file, without a path or a location, but with an extension if relevant. |
| TargetFilePath | string | The full, normalized path of the target file, including the folder or location, the file name, and the extension. |
| TargetFilePathType | string | The type of TargetFilePath. |
| TargetFileSHA1 | string | The SHA-1 hash of the target file. |
| TargetFileSHA256 | string | The SHA-256 hash of the target file. |
| TargetFileSHA512 | string | The SHA-512 hash of the source file. |
| TargetFileSize | long | The size of the target file in bytes. |
| TargetOriginalAppType | string | The target application type as reported by the reporting device. |
| TargetUrl | string | When the operation is initiated using HTTP or HTTPS, the URL used. |
| TenantId | string | The Log Analytics workspace ID |
| ThreatCategory | string | The category of the threat or malware identified in the file activity. |
| ThreatConfidence | int | The confidence level of the threat identified, normalized to a value between 0 and a 100. |
| ThreatField | string | The field for which a threat was identified. The value is either SrcFilePath or DstFilePath. |
| ThreatFilePath | string | A file path for which a threat was identified. The field ThreatField contains the name of the field ThreatFilePath represents. |
| ThreatFirstReportedTime | datetime | The first time the IP address or domain were identified as a threat. |
| ThreatId | string | The ID of the threat or malware identified in the file activity. |
| ThreatIsActive | bool | True ID the threat identified is considered an active threat. |
| ThreatLastReportedTime | datetime | The last time the IP address or domain were identified as a threat. |
| ThreatName | string | The name of the threat or malware identified in the file activity. |
| ThreatOriginalConfidence | string | The original confidence level of the threat identified, as reported by the reporting device. |
| ThreatOriginalRiskLevel | string | The risk level as reported by the reporting device. |
| ThreatRiskLevel | int | The risk level associated with the identified threat. The level should be a number between 0 and 100. |
| TimeGenerated | datetime | The timestamp reflecting the time in which the event was generated. |
| Type | string | The name of the table |
