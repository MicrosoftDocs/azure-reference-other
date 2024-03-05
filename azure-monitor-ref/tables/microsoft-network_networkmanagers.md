---
title: Azure Monitor tables for microsoft.network/networkmanagers
description: Azure Monitor tables for resource type microsoft.network/networkmanagers
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.network/networkmanagers  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AVNMConnectivityConfigurationChange](/azure/azure-monitor/reference/tables/AVNMConnectivityConfigurationChange)<p>Includes logs related to application or removal of connectivity configuration, on network resources like a virtual network. | resources, network, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/avnmconnectivityconfigurationchange)|
| [AVNMIPAMPoolAllocationChange](/azure/azure-monitor/reference/tables/AVNMIPAMPoolAllocationChange)<p>Includes changes to allocations of an IPAM Pool such as Virtual Networks, static CIDRs, or child pools. | resources, network, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/avnmipampoolallocationchange)|
| [AVNMNetworkGroupMembershipChange](/azure/azure-monitor/reference/tables/AVNMNetworkGroupMembershipChange)<p>Includes changes to network group membership of network resources like a virtual network. | resources, network, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/avnmnetworkgroupmembershipchange)|
| [AVNMRuleCollectionChange](/azure/azure-monitor/reference/tables/AVNMRuleCollectionChange)<p>Include logs related to application or removal of rule collections, on network resources like a virtual network or a subnet. | resources, network, audit | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/avnmrulecollectionchange)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

