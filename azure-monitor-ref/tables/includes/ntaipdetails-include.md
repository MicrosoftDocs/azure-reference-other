---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: NTAIpDetails
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| DnsDomain | string | For Malicious IPs only: Domain name associated with this IP. |
| FaSchemaVersion | string | Schema version. |
| FlowIntervalEndTime | datetime | End time of the flow log processing interval. |
| FlowIntervalStartTime | datetime | Start time of the flow log processing interval. This is time from which flow interval is measured. |
| FlowType | string | Can be AzurePublic/ExternalPublic/MaliciousFlow. |
| Ip | string | Public IP whose information is provided in the record. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | For Azure Public IP: Azure region of virtual network/network interface/virtual machine to which the IP belongs OR Global for IP 168.63.129.16. For External Public IP and Malicious IP: 2-letter country code where IP is located (ISO 3166-1 alpha-2). |
| Port | int | For Malicious IPs only: Port associated with this IP. |
| PublicIpDetails | string | For AzurePublic IP: Azure Service owning the IP OR "Microsoft Virtual Public IP" for IP 168.63.129.16 . ExternalPublic/Malicious IP: WhoIS information of the IP. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubType | string | Subtype for the flow logs. Use only FlowLog, other values of SubType_s are for internal workings of the product. |
| TenantId | string | The Log Analytics workspace ID |
| ThreatDescription | string | For Malicious IPs only: Description of the threat posed by the malicious IP. |
| ThreatType | string | For Malicious IPs only: One of the threats from the list of currently allowed values. |
| TimeGenerated | datetime | The time when the data gets ingested into the Log Analytics Workspace. |
| Type | string | The name of the table |
| Url | string | For Malicious IPs only: Url associated with this IP. |
