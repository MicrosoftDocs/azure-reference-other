---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ASimRegistryEventLogs
---


| Column | Type | Description |
|---|---|---|
| ActingProcessCommandLine | string | The command line used to run the process. |
| ActingProcessGuid | string | A generated unique identifier of the acting process. |
| ActingProcessId | string | The process ID of the acting process. |
| ActingProcessName | string | The file name of the acting process image file. |
| ActorOriginalUserType | string | The original actor user type, if provided by the source. |
| ActorScope | string | The scope, such as Azure AD tenant, in which ActorUserId and ActorUsername are defined. |
| ActorScopeId | string | The scope ID, such as Azure AD tenant ID, in which ActorUserId and ActorUsername are defined. |
| ActorSessionId | string | The unique ID of the login session of the Actor. |
| ActorUserAadId | string | The Azure Active Directory ID of the actor. |
| ActorUserId | string | A unique ID of the Actor. |
| ActorUserIdType | string | The type of the ID stored in the ActorUserId field. |
| ActorUsername | string | The user name of the user who initiated the event. |
| ActorUsernameType | string | Specifies the type of the user name stored in the ActorUsername field. |
| ActorUserSid | string | The Windows user ID (SIDs) of the actor. |
| ActorUserType | string | The type of the Actor.  |
| AdditionalFields | dynamic | Additional information, represented using key/value pairs provided by the source which do not map to ASim. |
| _BilledSize | real | The record size in bytes |
| DvcAction | string | For reporting security systems, the action taken by the system. |
| DvcDescription | string | A descriptive text associated with the device. |
| DvcDomain | string | The domain of the device reporting the event. |
| DvcDomainType | string | The type of DvcDomain. |
| DvcFQDN | string | The hostname of the device on which the event occurred or which reported the event. |
| DvcHostname | string | The hostname of the device reporting the event. |
| DvcId | string | The unique ID of the device on which the event occurred or which reported the event. |
| DvcIdType | string | The type of DvcId. |
| DvcInterface | string | The network interface on which data was captured. |
| DvcIpAddr | string | The IP Address of the device reporting the event. |
| DvcMacAddr | string | The MAC address of the device on which the event occurred or which reported the event. |
| DvcOriginalAction | string | The original DvcAction as provided by the reporting device. |
| DvcOs | string | The operating system running on the device on which the event occurred or which reported the event. |
| DvcOsVersion | string | The version of the operating system on the device on which the event occurred or which reported the event. |
| DvcScope | string | The cloud platform scope the device belongs to. DvcScope map to a subscription name on Azure and to an account ID on AWS. |
| DvcScopeId | string | The cloud platform scope ID the device belongs to. DvcScopeId map to a subscription ID on Azure and to an account ID on AWS. |
| DvcZone | string | The network on which the event occurred or which reported the event. |
| EventCount | int | The number of events described by the record. |
| EventEndTime | datetime | The time in which the event ended. If the source supports aggregation and the record represents multiple events, the time when the last event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventMessage | string | A general message or description. |
| EventOriginalResultDetails | string | The original result details provided by the source. |
| EventOriginalSeverity | string | The original severity as provided by the reporting device. |
| EventOriginalSubType | string | The original event subtype or ID, if provided by the source. |
| EventOriginalType | string | A unique ID of the original record, if provided by the source. |
| EventOriginalUid | string | . |
| EventOwner | string | The owner of the event, which is usually the department or subsidiary in which it was generated. |
| EventProduct | string | The product generating the event. |
| EventProductVersion | string | The version of the product generating the event. |
| EventReportUrl | string | A URL provided in the event for a resource that provides more information about the event. |
| EventResult | string | The outcome of the event, represented by one of the following values: Success, Partial, Failure, NA (Not Applicable). The value may not be provided directly by the sources, in which case it is derived from other event fields, for example, the EventResultDetails field. |
| EventResultDetails | string | Reason or details for the result reported in the EventResult field. |
| EventSchema | string | The name of the schema. |
| EventSchemaVersion | string | The version of the schema. |
| EventSeverity | string | The severity of the event. Valid values are: Informational, Low, Medium, or High. |
| EventStartTime | datetime | The time in which the event started. If the source supports aggregation and the record represents multiple events, the time when the first event was generated. If not provided by the source record, this field aliases the TimeGenerated field. |
| EventSubType | string | Describes a subdivision of the operation reported in the EventType field. |
| EventType | string | Describes the operation reported by the record. |
| EventVendor | string | The vendor of the product generating the event. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ParentProcessCommandLine | string | The command line used to run the process. |
| ParentProcessGuid | string | A generated unique identifier of the parent process. |
| ParentProcessId | string | The process ID of the parent process. |
| ParentProcessName | string | The file name of the parent process image file. |
| RegistryKey | string | The registry key associated with the operation, normalized to standard root key naming conventions. |
| RegistryPreviousKey | string | For operations that modify the registry, the original registry key, normalized to standard root key naming. |
| RegistryPreviousValue | string | For operations that modify the registry, the original value type, normalized to the standard form. |
| RegistryPreviousValueData | string | The original registry data, for operations that modify the registry. |
| RegistryPreviousValueType | string | For operations that modify the registry, the original value type. |
| RegistryValue | string | The registry value associated with the operation. |
| RegistryValueData | string | The data stored in the registry value. |
| RegistryValueType | string | The type of registry value, normalized to standard form. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RuleName | string | The name or ID of the rule by associated with the inspection results. |
| RuleNumber | int | The number of the rule associated with the inspection results. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
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
