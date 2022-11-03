---
title: Azure Monitor Logs reference - DeviceInfo
description: Reference for DeviceInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# DeviceInfo

 This table is part of Microsoft Defender for Endpoints with Azure Sentinel. This table contains Machine information, including OS information.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalFields | dynamic | Additional information about the entity or event. |
| ClientVersion | string | Version of the endpoint agent or sensor running on the machine. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| DeviceObjectId | string | Unique identifier for the device in Azure AD. |
| IsAzureADJoined | bool | Boolean indicator of whether machine is joined to the Azure Active Directory. |
| LoggedOnUsers | dynamic | List of all users that are logged on the machine at the time of the event in JSON array format. |
| MachineGroup | string | Machine group used to determine access to the machine and apply group-specific settings. |
| OSArchitecture | string | Architecture of the operating system running on the machine. |
| OSBuild | long | Build version of the operating system running on the machine. |
| OSPlatform | string | Platform of the operating system running on the machine. This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7. |
| OSVersion | string | Version of the operating system running on the machine. |
| PublicIP | string | Public IP address used by the onboarded machine to connect to the Windows Defender ATP service. This could be the IP address of the machine itself, a NAT device, or a proxy. |
| RegistryDeviceTag | string | Device tag added through the registry. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns.. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the record was generated. |
| Type | string | The name of the table |
