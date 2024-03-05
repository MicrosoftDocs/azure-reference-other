---
title: Azure Monitor tables for microsoft.insights/datacollectionrules
description: Azure Monitor tables for resource type microsoft.insights/datacollectionrules
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
   
ms.date: 03/05/2024


---

# Resource log tables for microsoft.insights/datacollectionrules  


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [DCRLogErrors](/azure/azure-monitor/reference/tables/DCRLogErrors)<p>Errors registered during DCR-based data collection and transformation. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/dcrlogerrors)|
| [DCRLogTroubleshooting](/azure/azure-monitor/reference/tables/DCRLogTroubleshooting)<p>Logs from DCR-based data collection and transformation to help with troubleshooting of DCR configuration and flow. | resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/dcrlogtroubleshooting)|

