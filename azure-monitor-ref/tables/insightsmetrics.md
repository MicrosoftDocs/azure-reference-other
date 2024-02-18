---
title: Azure Monitor Logs reference - InsightsMetrics
description: Reference for InsightsMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
---

# InsightsMetrics

Table that stores metrics. 'Perf' table also stores many metrics and over time they all will converge to InsightsMetrics for Azure Monitor Solutions 


## Categories

- Virtual Machines
- Containers
- Azure Resources

## Solutions

- AzureResources
- ContainerInsights
- InfrastructureInsights
- LogManagement
- ServiceMap
- VMInsights

## Resource types

- Azure Arc Enabled Kubernetes
- Kubernetes Services
- Workload Monitoring of Azure Monitor Insights
- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets
- Azure Arc Provisioned Clusters
- IoT Hub

## Queries

 Sample queries for the [InsightsMetrics](../queries/insightsmetrics.md) table.


## Columns
  
[!INCLUDE [insightsmetrics](.././tables/includes/insightsmetrics-include.md)]
