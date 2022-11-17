---
title: Azure Monitor Logs reference - AmlOnlineEndpointEventLog
description: Reference for AmlOnlineEndpointEventLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# AmlOnlineEndpointEventLog

 Azure ML online endpoints event logs. It provides event logs regarding the inference-server container's life cycle.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Machine Learning




## Columns

| Column | Type | Description |
| --- | --- | --- |
| DeploymentName | string | The name of the deployment associated with this log record. |
| InstanceId | string | The ID of the instance that generated this log record. |
| Message | string | The content of the inference-server container life cycle event. |
| Name | string | The name of the inference-server container life cycle event. |
| OperationName | string | The operation associated with this log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when this log was generated. |
| Type | string | The name of the table |
