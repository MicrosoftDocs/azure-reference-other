---
title: Azure Monitor Logs reference - ContainerLogV2
description: Reference for ContainerLogV2 table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
---

# ContainerLogV2

Kubernetes Container logs in V2 schema. This is the successor of ContainerLog. This has a friendlier schema, specifically for Kubernetes orchestrated containers in pods. With this feature enabled, previously split container logs are stitched together and sent as single entries to the ContainerLogV2 table. The schema now supports container log lines of up to to 64 KB. The schema also supports .NET and Go stack traces, which appear as single entries.


## Categories

- Containers

## Solutions

- AzureResources
- ContainerInsights

## Resource types

- Kubernetes Services
- Azure Arc Enabled Kubernetes
- Azure Arc Provisioned Clusters

## Queries

 Sample queries for the [ContainerLogV2](../queries/containerlogv2.md) table.


## Columns
  
[!INCLUDE [containerlogv2](.././tables/includes/containerlogv2-include.md)]
