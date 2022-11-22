---
title: Azure Monitor Logs reference - NSPAccessLogs
description: Reference for NSPAccessLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# NSPAccessLogs

 Logs of Network Security Perimeter (NSP) inbound access allowed based on NSP access rules.

## Categories

- Azure Resources
- Network
- Audit
- Security
## Solutions

- LogManagement
## Resource types

- Network Security Perimeters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AppId | string | Unique GUID representing the app ID of resource in the Azure Active Directory. |
| Category | string | NSP access log categories. |
| DestinationFqdn | string | Fully Qualified Domain(FQDN) name of the destination. |
| DestinationParameters | string | List of optional destination properties in key-value pair format. For example: [ {Param1}: {value1}, {Param2}: {value2}, ...]. |
| DestinationPort | string | Port number of outbound connection, when available. |
| DestinationProtocol | string | Application layer protocol and transport layer protocol used for outbound connection in the format {AppProtocol}:{TransportProtocol}. For example: 'HTTPS:TCP'. It be must specified if available. |
| DestinationResourceId | string | Resource ID of destination PaaS resource for an outbound connection, when available. |
| Location | string | Indicates the region of NSP. |
| MatchedRule | string | JSON property bag containing matched access rule name. It can be either NSP access rule name or resource rule name (not it's resource ID). |
| OperationName | string | Indicates top-level PaaS operation name. |
| OperationVersion | string | The API version associated with the operation. |
| Parameters | string | List of optional PaaS resource properties in key-value pair format. For example: [ {Param1}: {value1}, {Param2}: {value2}, ...]. |
| Profile | string | Name of the NSP profile associated to the resource. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultAction | string | Indicates whether the result of evaluation is 'Approved' or 'Denied'. |
| ResultDescription | string | Additional description about the operation result, when available. |
| ResultDirection | string | Direction of evaluation result whether 'Inbound' or 'Outbound'. |
| RuleType | string | Indicates where the rule is defined: NSP or PaaS resource. |
| ServiceResourceId | string | Resource ID of PaaS resource emitting NSP access logs. |
| SourceAppId | string | Unique GUID representing the app ID of source in the Azure Active Directory. |
| SourceIpAddress | string | IP address of source making inbound connection, when available. |
| SourceParameters | string | List of optional source properties in key-value pair format. For example: [ {Param1}: {value1}, {Param2}: {value2}, ...]. |
| SourcePerimeterGuids | string | List of perimeter GUIDs of source resource. It should be specified only if allowed based on perimeter GUID. |
| SourcePort | string | Port number of inbound connection, when available. |
| SourceProtocol | string | Application layer protocol and transport layer protocol used for inbound connection in the format {AppProtocol}:{TransportProtocol}. For example: 'HTTPS:TCP'. It be must specified if available. |
| SourceResourceId | string | Resource ID of source PaaS resource for an inbound connection, when available. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Event generation time. |
| TrafficType | string | Indicates whether traffic is 'Private', 'Public' or 'Intra-Perimeter'. |
| Type | string | The name of the table |
