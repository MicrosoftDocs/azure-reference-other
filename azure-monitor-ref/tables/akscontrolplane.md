---
title: Azure Monitor Logs reference - AKSControlPlane
description: Reference for AKSControlPlane table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/19/2023
---

# AKSControlPlane

 Contains diagnostic logs for the Kubernetes API Server, Controller Manager, Scheduler, Cluster Autoscaler, Cloud Controller Manager, Guard, and the Azure CSI storage drivers. These diagnostic logs have distinct Category entries corresponding their diagnostic log setting (e.g. kube-apiserver, kube-audit-admin).

## Categories

- Azure Resources
- Containers
## Solutions

- LogManagement
## Resource types

- Kubernetes Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Service log category describing the service logging the message. |
| Level | string | Level (Fatal, Error, Warning, Info) of the log message. |
| Message | string | Log message body. |
| PodName | string | Name of the pod logging the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Stream | string | Output stream (stdout, stderr) source of the log message. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Event generation time. |
| Type | string | The name of the table |
