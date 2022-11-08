---
title: Azure Monitor Logs reference - VMComputer
description: Reference for VMComputer table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# VMComputer

 Inventory data for servers collected by the Service Map and VM Insights solutions using the Dependency agent and Log analytics agent.

## Categories

- Virtual Machines
## Solutions

- AzureResources
- Service Map
- Azure Monitor for VMs
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AgentId | string | Unique ID for the microsoft monitoring agent installed on the server. |
| AzureCloudServiceDeployment | string | For cloud services the deployment id of the server. |
| AzureCloudServiceInstanceId | string | For cloud services the instance name of the server. |
| AzureCloudServiceName | string | For cloud services the service name of the server. |
| AzureCloudServiceRoleName | string | For cloud services the role name of the server. |
| AzureCloudServiceRoleType | string | For cloud services the role type of the server. |
| AzureFaultDomain | string | The fault domain for the server. Only available for Azure VMs and VMSS instances. |
| AzureImageOffering | string | The description of the image used on the server. Only available for Azure VMs and VMSS instances. |
| AzureImagePublisher | string | The publisher of the VM image used on the server. Only available for Azure VMs and VMSS instances. |
| AzureImageSku | string | The sku for the VM image used on the server. Only available for Azure VMs and VMSS instances. |
| AzureImageVersion | string | The image version used on the server. Only available for Azure VMs and VMSS instances. |
| AzureLocation | string | The location of the server. Only available for Azure VMs and VMSS instances. |
| AzureResourceGroup | string | The resource group for the server. Only available for Azure VMs and VMSS instances. |
| AzureResourceName | string | The Azure name for the resource. |
| AzureServiceFabricClusterId | string | For service fabric clusters the cluster id of the server. |
| AzureServiceFabricClusterName | string | For service fabric clusters the cluster name. |
| AzureSize | string | The size of the Azure VM.�Only available for Azure VMs and VMSS instances. |
| AzureSubscriptionId | string | The subscription ID of the server. Only available for Azure VMs and VMSS instances. |
| AzureUpdateDomain | string | The update domain of the server. Only available for Azure VMs and VMSS instances. |
| AzureVmId | string | The Azure ID of the server. Only available for Azure VMs and VMSS instances. |
| AzureVmScaleSetDeployment | string | For scale sets the deployment id of the server. |
| AzureVmScaleSetInstanceId | string | For scale sets the instance id of the server. |
| AzureVmScaleSetName | string | For scale sets the name of the scale set. |
| AzureVmScaleSetResourceId | string | For scale sets the resource id of the scale set. |
| BootTime | datetime | The boot time in UTC |
| Computer | string | The name of the computer. |
| Cpus | int | The number of CPUs |
| CpuSpeed | int | The CPU speed in MHz |
| DependencyAgentVersion | string | The version number of the dependency agent on the server. |
| DisplayName | string | The display name of the server. |
| DnsNames | dynamic | An array of DNS names |
| FullDisplayName | string | The full display name of the server. |
| HostingProvider | string | The hosting provider for the server |
| HostName | string | The host name of the server without domain. |
| HypervisorId | string | The hypervisor id of the server. |
| HypervisorType | string | The hypervisor type of the server. |
| Ipv4Addresses | dynamic | A list of the server's IPv4 addresses |
| Ipv4DefaultGateways | dynamic | A list of the server's IPv4 default gateways. |
| Ipv4SubnetMasks | dynamic | A list of the server's IPv4 subnet masks. |
| Ipv6Addresses | dynamic | A list of the server's IPv6 addresses |
| MacAddresses | dynamic | A list of the server's MAC addresses |
| Machine | string | AgentId with m- prepended. |
| OperatingSystemFamily | string | Value will be windows or linux |
| OperatingSystemFullName | string | The full name of the operating system |
| PhysicalMemoryMB | long | The physical memory in MB |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The source of the data collected (Insights) |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TimeZone | string | The UTC timezone offset of the server. |
| Type | string | The name of the table |
| VirtualizationState | string | Values will be Unknown Physical Virtual or Hypervisor |
| VirtualMachineHypervisorId | string | The hypervisor id of the server. |
| VirtualMachineNativeId | string | The native id of the server. |
| VirtualMachineNativeName | string | The name of the VM |
| VirtualMachineType | string | hyperv vmware xen and so on |
