---
title: Azure Monitor Logs reference - DeviceNetworkInfo
description: Reference for DeviceNetworkInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/2/2023
---

# DeviceNetworkInfo

 Microsoft Defender for Endpoints (MDE) device network information table. This table contains Network properties of machines, including adapters, IP and MAC addresses, as well as connected networks and domains.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ConnectedNetworks | dynamic | Networks that the adapter is connected to. Each JSON element in the array contains the network name, category (public, private or domain), a description, and a flag indicating if it is connected publicly to the internet. |
| DefaultGateways | dynamic | Default gateway addresses in JSON array format. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| DnsAddresses | dynamic | DNS server addresses in JSON array format. |
| IPAddresses | dynamic | JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and the IP class (RFC 1918 & RFC 4291). |
| IPv4Dhcp | string | IPv4 address of the configured DHCP server. |
| IPv6Dhcp | string | IPv6 address of the configured DHCP server. |
| MacAddress | string | MAC address of the network adapter. |
| MachineGroup | string | The machine-group which this machine is associated to. This group is used by role-based access control to determine access to the machine. |
| NetworkAdapterName | string | Name of the network adapter. |
| NetworkAdapterStatus | string | Operational status of the network adapter. |
| NetworkAdapterType | string | Network adapter type. |
| NetworkAdapterVendor | string | Name of the manufacturer or vendor of the network adapter. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the DeviceName and/or Timestamp columns. |
| SourceSystem | string |  |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time the event was recorded by the MDE agent on the endpoint. |
| TunnelType | string | Tunneling protocol, when the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH. |
| Type | string | The name of the table |
