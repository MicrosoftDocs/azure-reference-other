---
title: Azure Monitor Logs reference - ArcK8sAuditAdmin
description: Reference for ArcK8sAuditAdmin table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024
---

# ArcK8sAuditAdmin

Contains Kubernetes API Server audit logs excluding events with the get and list verbs. These events are useful for monitoring resource modification requests made to the Kubernetes API. To see all modifying and non-modifying operations see the ArcK8sAudit table. Requires Diagnostic Settings to use the Resource Specific destination table.


## Categories

- Audit
- Azure Resources
- Containers

## Solutions

- LogManagement

## Resource types

- Azure Arc Enabled Kubernetes

## Columns
  
[!INCLUDE [arck8sauditadmin](.././tables/includes/arck8sauditadmin-include.md)]
