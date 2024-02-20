---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: ThreatIntelligenceIndicator
---


| Column | Type | Description |
|---|---|---|
| Action | string | Action to take on indicator match. |
| Active | bool | Indicates whether indicator is active. |
| ActivityGroupNames | string | Activity groups associated with indicator. |
| AdditionalInformation | string | Free text additional information for indicator. |
| _BilledSize | real | The record size in bytes |
| ConfidenceScore | real | Confidence rating of the indicator, from 0 to 100. |
| Description | string | Description of the indicator. |
| DiamondModel | string | Diamond model value for the indicator, one of adversary, capability, infrastructure or victim. |
| DomainName | string | The domain name observable. |
| EmailEncoding | string | The email encoding observable. |
| EmailLanguage | string | The email language observable. |
| EmailRecipient | string | The email recipient observable. |
| EmailSenderAddress | string | The email sender address observable. |
| EmailSenderName | string | The email sender name observable. |
| EmailSourceDomain | string | The email source domain observable. |
| EmailSourceIpAddress | string | The email source IP address observable. |
| EmailSubject | string | The email subject observable. |
| EmailXMailer | string | The email X-Mailer observable. |
| ExpirationDateTime | datetime | Time of indicator expiration. |
| ExternalIndicatorId | string | Identifier for indicator from submitting system. |
| FileCompileDateTime | datetime | The file compilation time observable. |
| FileCreatedDateTime | datetime | The file creation time observable. |
| FileHashType | string | The file hash type observable. |
| FileHashValue | string | The file hash value observable. |
| FileMutexName | string | The file mutex name observable. |
| FileName | string | The file name observable. |
| FilePacker | string | The file packer observable. |
| FilePath | string | The file path observable. |
| FileSize | int | The file size observable. |
| FileType | string | The file type observable. |
| IndicatorId | string | Unique identifier for indicator, calculated by receiving system. |
| IndicatorProvider | string | The name of the entity that provided the indicator. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KillChainActions | bool | Indicates whether kill chain value 'actions' is set. |
| KillChainC2 | bool | Indicates whether kill chain value 'C2' is set. |
| KillChainDelivery | bool | Indicates whether kill chain value 'delivery' is set. |
| KillChainExploitation | bool | Indicates whether kill chain value 'exploitation' is set. |
| KillChainReconnaissance | bool | Indicates whether kill chain value 'reconniassance' is set. |
| KillChainWeaponization | bool | Indicates whether kill chain value 'weaponization' is set. |
| KnownFalsePositives | string | Text describing situations where indicator may cause false positives. |
| MalwareNames | string | List of malware names associated with indicator |
| NetworkCidrBlock | string | The network CIDR block observable. |
| NetworkDestinationAsn | int | The network destination autonomous system number observable. |
| NetworkDestinationCidrBlock | string | The network destination CIDR block observable. |
| NetworkDestinationIP | string | The network destination IP address. |
| NetworkDestinationPort | int | The network destination port observable. |
| NetworkIP | string | The network IP address observable. |
| NetworkPort | int | The network port observable. |
| NetworkProtocol | int | The network protocol observable. |
| NetworkSourceAsn | int | The network source autonomous system number observable. |
| NetworkSourceCidrBlock | string | The network source CIDR block observable. |
| NetworkSourceIP | string | The network source IP address observable. |
| NetworkSourcePort | int | The network source port observable. |
| PassiveOnly | bool | Indicates whether the indicator should trigger an event that is visible to a user. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Tags | string | Free form tags. |
| TenantId | string | The Log Analytics workspace ID |
| ThreatSeverity | int | Indicator severity rating from 0 to 5. Higher value indicates greater severity. |
| ThreatType | string | Threat type of indicator. |
| TimeGenerated | datetime | Time of indicator ingestion. |
| TrafficLightProtocolLevel | string | Industry standard traffic light protocol level, one of white, green, amber or red. |
| Type | string | The name of the table |
| Url | string | The url observable. |
| UserAgent | string | The user agent observable. |
