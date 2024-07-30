---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DeviceNetworkInfo
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ConnectedNetworks | dynamic | Networks that the adapter is connected to. Each JSON element in the array contains the network name, category (public, private or domain), a description, and a flag indicating if it is connected publicly to the internet. |
| DefaultGateways | dynamic | Default gateway addresses in JSON array format. |
| DeviceId | string | Unique identifier for the device in the service. |
| DeviceName | string | Fully qualified domain name (FQDN) of the device. |
| DnsAddresses | dynamic | DNS server addresses in JSON array format. |
| IPAddresses | dynamic | JSON array containing all the IP addresses assigned to the adapter, along with their respective subnet prefix and the IP class (RFC 1918 & RFC 4291). |
| IPv4Dhcp | string | IPv4 address of the configured DHCP server. |
| IPv6Dhcp | string | IPv6 address of the configured DHCP server. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| MacAddress | string | MAC address of the network adapter. |
| MachineGroup | string | The machine-group which this machine is associated to. This group is used by role-based access control to determine access to the machine. |
| NetworkAdapterName | string | Name of the network adapter. |
| NetworkAdapterStatus | string | Operational status of the network adapter. |
| NetworkAdapterType | string | Network adapter type. |
| NetworkAdapterVendor | string | Name of the manufacturer or vendor of the network adapter. |
| ReportId | long | Event identifier based on a repeating counter. To identify unique events, this column must be used in conjunction with the DeviceName and/or Timestamp columns. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time the event was recorded by the MDE agent on the endpoint. |
| TunnelType | string | Tunneling protocol, when the interface is used for this purpose, for example 6to4, Teredo, ISATAP, PPTP, SSTP, and SSH. |
| Type | string | The name of the table |
