---
title: Azure Monitor Logs reference - AmlOnlineEndpointEventLog
description: Reference for AmlOnlineEndpointEventLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
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
| _BilledSize | real |  |
| DeploymentName | string | The name of the deployment associated with this log record. |
| InstanceId | string | The ID of the instance that generated this log record. |
| _IsBillable | string |  |
| Message | string | The content of the inference-server container life cycle event. |
| Name | string | The name of the inference-server container life cycle event. |
| OperationName | string | The operation associated with this log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when this log was generated. |
| Type | string | The name of the table |
