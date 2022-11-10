---
title: Azure Monitor Logs reference - DeviceNetworkInfo
description: Reference for DeviceNetworkInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# DeviceNetworkInfo

 This table is part of Microsoft Defender for Endpoints with Azure Sentinel. This table contains Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ConnectedNetworks | dynamic | Networks that the adapter is connected to. Each JSON element in the array contains the network name, category (public, private or domain), a description, and a flag indicating if itâ€™s connected publicly to the internet. |
| DefaultGateways | dynamic | Default gateway addresses in JSON array format. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| DnsAddresses | dynamic | DNS server addresses in JSON array format. |
| IPAddresses | dynamic | JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and the IP class (RFC 1918 & RFC 4291). |
| IPv4Dhcp | string | IPv4 address of DHCP server. |
| IPv6Dhcp | string | IPv6 address of DHCP server. |
| MacAddress | string | MAC address of the network adapter. |
| MachineGroup | string | Machine group of the machine. This group is used by role-based access control to determine access to the machine. |
| NetworkAdapterName | string | Name of the network adapter. |
| NetworkAdapterStatus | string | Operational status of the network adapter. |
| NetworkAdapterType | string | Network adapter type. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the ComputerName and EventTime columns.. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the record was generated. |
| TunnelType | string | Tunneling protocol, if the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH. |
| Type | string | The name of the table |
