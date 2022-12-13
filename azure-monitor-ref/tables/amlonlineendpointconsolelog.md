---
title: Azure Monitor Logs reference - AmlOnlineEndpointConsoleLog
description: Reference for AmlOnlineEndpointConsoleLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AmlOnlineEndpointConsoleLog

 All console logs for AzureML online endpoints.

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
| ContainerName | string | The name of the container where the log was generated. |
| DeploymentName | string | The name of the deployment associated with the log record. |
| InstanceId | string | The ID of the instance that generated this log record. |
| Message | string | The content of the log. |
| OperationName | string | The operation associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
