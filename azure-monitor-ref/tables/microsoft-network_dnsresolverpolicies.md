---
title: Azure Monitor tables for microsoft.network/dnsresolverpolicies
description: Azure Monitor tables for resource type microsoft.network/dnsresolverpolicies
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.network/dnsresolverpolicies  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [DNSQueryLogs](/azure/azure-monitor/reference/tables/DNSQueryLogs)<p>DNS query logs enable customers to monitor the DNS traffic in their virtual networks and help securing their DNS infrastructure. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/dnsquerylogs)|

