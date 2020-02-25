---
title: Azure Monitor Logs reference - VMComputer
description: Reference for VMComputer table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# VMComputer

 Inventory data for servers collected by the Service Map and VM Insights solutions using the Dependency agent and Log analytics agent.

## Columns

|Column|Type|Description|
|---|---|---|
|TimeGenerated|datetime|Date and time the record was created.|
|Computer|string|The name of the computer.|
|AgentId|string|Unique ID for the microsoft monitoring agent installed on the server.|
|Machine|string|AgentId with m- prepended.|
|DisplayName|string|The display name of the server.|
|FullDisplayName|string|The full display name of the server.|
|HostName|string|The host name of the server without domain.|
|BootTime|datetime|The boot time in UTC|
|TimeZone|string|The UTC timezone offset of the server.|
|VirtualizationState|string|Values will be Unknown Physical Virtual or Hypervisor|
|Ipv4Addresses|dynamic|A list of the server's IPv4 addresses|
|Ipv4SubnetMasks|dynamic|A list of the server's IPv4 subnet masks.|
|Ipv4DefaultGateways|dynamic|A list of the server's IPv4 default gateways.|
|Ipv6Addresses|dynamic|A list of the server's IPv6 addresses|
|MacAddresses|dynamic|A list of the server's MAC addresses|
|DnsNames|dynamic|An array of DNS names|
|DependencyAgentVersion|string|The version number of the dependency agent on the server.|
|OperatingSystemFamily|string|Value will be windows or linux|
|OperatingSystemFullName|string|The full name of the operating system|
|PhysicalMemoryMB|long|The physical memory in MB|
|Cpus|int|The number of CPUs|
|CpuSpeed|int|The CPU speed in MHz|
|VirtualMachineType|string|hyperv vmware xen and so on|
|VirtualMachineNativeId|string|The native id of the server.|
|VirtualMachineNativeName|string|The name of the VM|
|VirtualMachineHypervisorId|string|The hypervisor id of the server.|
|HypervisorType|string|The hypervisor type of the server.|
|HypervisorId|string|The hypervisor id of the server.|
|HostingProvider|string|The hosting provider for the server|
|AzureSubscriptionId|string|The subscription ID of the server. Only available for Azure VMs and VMSS instances.|
|AzureResourceGroup|string|The resource group for the server. Only available for Azure VMs and VMSS instances.|
|AzureResourceName|string|The Azure name for the resource.|
|AzureLocation|string|The location of the server. Only available for Azure VMs and VMSS instances.|
|AzureUpdateDomain|string|The update domain of the server. Only available for Azure VMs and VMSS instances.|
|AzureFaultDomain|string|The fault domain for the server. Only available for Azure VMs and VMSS instances.|
|AzureVmId|string|The Azure ID of the server. Only available for Azure VMs and VMSS instances.|
|AzureSize|string|The size of the Azure VM. Only available for Azure VMs and VMSS instances.|
|AzureImagePublisher|string|The publisher of the VM image used on the server. Only available for Azure VMs and VMSS instances.|
|AzureImageOffering|string|The description of the image used on the server. Only available for Azure VMs and VMSS instances.|
|AzureImageSku|string|The sku for the VM image used on the server. Only available for Azure VMs and VMSS instances.|
|AzureImageVersion|string|The image version used on the server. Only available for Azure VMs and VMSS instances.|
|AzureCloudServiceName|string|For cloud services the service name of the server.|
|AzureCloudServiceDeployment|string|For cloud services the deployment id of the server.|
|AzureCloudServiceRoleName|string|For cloud services the role name of the server.|
|AzureCloudServiceRoleType|string|For cloud services the role type of the server.|
|AzureCloudServiceInstanceId|string|For cloud services the instance name of the server.|
|AzureVmScaleSetName|string|For scale sets the name of the scale set.|
|AzureVmScaleSetDeployment|string|For scale sets the deployment id of the server.|
|AzureVmScaleSetResourceId|string|For scale sets the resource id of the scale set.|
|AzureVmScaleSetInstanceId|string|For scale sets the instance id of the server.|
|AzureServiceFabricClusterId|string|For service fabric clusters the cluster id of the server.|
|AzureServiceFabricClusterName|string|For service fabric clusters the cluster name.|
|SourceSystem|string|The source of the data collected (Insights)|
|Type|string||
|_ResourceId|string||
