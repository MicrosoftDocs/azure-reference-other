---
title: Azure Monitor Logs reference - ArcK8sControlPlane
description: Reference for ArcK8sControlPlane table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 12/18/2023
---

# ArcK8sControlPlane

Contains diagnostic logs for the Kubernetes API Server, Controller Manager, Scheduler, Cluster Autoscaler, Cloud Controller Manager, Guard, and the Azure CSI storage drivers. These diagnostic logs have distinct Category entries corresponding their diagnostic log setting (e.g. kube-apiserver, kube-audit-admin). Requires Diagnostic Settings to use the Resource Specific destination table.

## Categories

- Azure Resources
- Containers
## Solutions

- LogManagement
## Resource types

- Azure Arc Enabled Kubernetes

            


## Columns
  
[!INCLUDE [arck8scontrolplane](../includes/arck8scontrolplane-include.md)]
