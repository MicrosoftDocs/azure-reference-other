---
title: Azure Monitor tables for microsoft.network/azurefirewalls
description: Azure Monitor tables for resource type microsoft.network/azurefirewalls
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.network/azurefirewalls  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AZFWApplicationRule](/azure/azure-monitor/reference/tables/AZFWApplicationRule)<p>Contains all Application rule log data. Each match between data plane and Application rule creates a log entry with the data plane packet and the matched rule's attributes. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwapplicationrule)|
| [AZFWApplicationRuleAggregation](/azure/azure-monitor/reference/tables/AZFWApplicationRuleAggregation)<p>Contains aggregated Application rule log data for Policy Analytics. | security | LogManagement | No| -|
| [AZFWDnsQuery](/azure/azure-monitor/reference/tables/AZFWDnsQuery)<p>Contains all DNS Proxy events log data. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwdnsquery)|
| [AZFWFatFlow](/azure/azure-monitor/reference/tables/AZFWFatFlow)<p>This query returns the top flows across Azure Firewall instances. Log contains flow information, date transmission rate (in Megabits per second units) and the time period when the flows were recorded. Please follow the documentation to enable Top flow logging and details on how it is recorded. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwfatflow)|
| [AZFWFlowTrace](/azure/azure-monitor/reference/tables/AZFWFlowTrace)<p>Flow logs across Azure Firewall instances. Log contains flow information, flags and the time period when the flows were recorded. Please follow the documentation to enable flow trace logging and details on how it is recorded. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/azfwflowtrace)|
| [AZFWIdpsSignature](/azure/azure-monitor/reference/tables/AZFWIdpsSignature)<p>Contains all data plane packets that were matched with one or more IDPS signatures. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwidpssignature)|
| [AZFWInternalFqdnResolutionFailure](/azure/azure-monitor/reference/tables/AZFWInternalFqdnResolutionFailure)<p>Contains all internal Firewall FQDN resolution requests that resulted in failure. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwinternalfqdnresolutionfailure)|
| [AZFWNatRule](/azure/azure-monitor/reference/tables/AZFWNatRule)<p>Contains all DNAT (Destination Network Address Translation) events log data. Each match between data plane and DNAT rule creates a log entry with the data plane packet and the matched rule's attributes. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwnatrule)|
| [AZFWNatRuleAggregation](/azure/azure-monitor/reference/tables/AZFWNatRuleAggregation)<p>Contains aggregated NAT Rule log data for Policy Analytics. | security | LogManagement | No| -|
| [AZFWNetworkRule](/azure/azure-monitor/reference/tables/AZFWNetworkRule)<p>Contains all Network Rule log data. Each match between data plane and network rule creates a log entry with the data plane packet and the matched rule's attributes. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwnetworkrule)|
| [AZFWNetworkRuleAggregation](/azure/azure-monitor/reference/tables/AZFWNetworkRuleAggregation)<p>Contains aggregated Network rule log data for Policy Analytics. | security | LogManagement | No| -|
| [AZFWThreatIntel](/azure/azure-monitor/reference/tables/AZFWThreatIntel)<p>Contains all Threat Intelligence events. | security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azfwthreatintel)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

