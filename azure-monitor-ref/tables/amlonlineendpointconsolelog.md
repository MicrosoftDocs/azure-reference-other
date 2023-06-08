---
title: Azure Monitor Logs reference - AmlOnlineEndpointConsoleLog
description: Reference for AmlOnlineEndpointConsoleLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AmlOnlineEndpointConsoleLog

 Azure ML online endpoints console logs. It provides console logs output from user containers.

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
| ContainerImageName | string | The name of the docker image running in the container where the log was generated. |
| ContainerName | string | The name of the container where the log was generated. |
| DeploymentName | string | The name of the deployment associated with the log record. |
| InstanceId | string | The ID of the instance that generated this log record. |
| _IsBillable | string |  |
| Message | string | The content of the log. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
