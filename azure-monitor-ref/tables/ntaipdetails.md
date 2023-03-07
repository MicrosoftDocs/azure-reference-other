---
title: Azure Monitor Logs reference - NTAIpDetails
description: Reference for NTAIpDetails table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/2/2023
---

# NTAIpDetails

 Traffic Analytics provides WHOIS data and geographic location for all public IPs in the customer's environment. For Malicious IP, it provides DNS domain, threat type and thread descriptions as identified by Microsoft security intelligence solutions. IP Details are published to your Log Analytics Workspace so you can create custom queries and put alerts on them. You can also access pre-populated queries from the traffic analytics dashboard.

## Categories

- Network
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| DnsDomain | string | For Malicious IPs only: Domain name associated with this IP. |
| FaSchemaVersion | string | Schema version. |
| FlowIntervalEndTime | datetime | End time of the flow log processing interval. |
| FlowIntervalStartTime | datetime | Start time of the flow log processing interval. This is time from which flow interval is measured. |
| FlowType | string | Can be AzurePublic/ExternalPublic/MaliciousFlow. |
| Ip | string | Public IP whose information is provided in the record. |
| Location | string | For Azure Public IP: Azure region of virtual network/network interface/virtual machine to which the IP belongs OR Global for IP 168.63.129.16. For External Public IP and Malicious IP: 2-letter country code where IP is located (ISO 3166-1 alpha-2). |
| PublicIpDetails | string | For AzurePublic IP: Azure Service owning the IP OR "Microsoft Virtual Public IP" for IP 168.63.129.16 . ExternalPublic/Malicious IP: WhoIS information of the IP. |
| SourceSystem | string |  |
| SubType | string | Subtype for the flow logs. Use only FlowLog, other values of SubType_s are for internal workings of the product. |
| TenantId | string |  |
| ThreatDescription | string | For Malicious IPs only: Description of the threat posed by the malicious IP. |
| ThreatType | string | For Malicious IPs only: One of the threats from the list of currently allowed values. |
| TimeGenerated | datetime | The time when the data gets ingested into the Log Analytics Workspace. |
| Type | string | The name of the table |
