---
title: Azure Monitor Logs reference - ADFSSISIntegrationRuntimeLogs
description: Reference for ADFSSISIntegrationRuntimeLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# ADFSSISIntegrationRuntimeLogs

 ADF SSIS integration runtime logs

## Solutions

- LogManagement
## Resource types

- Data factories




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The name of the log that belongs to |
| CorrelationId | string | correlation id |
| DataFactoryName | string | Data factory name |
| IntegrationRuntimeName | string | Integration runtime name |
| Level | string | Verbosity level of log |
| Message | string | Event message |
| OperationName | string | The name of the operation represented by this event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Status of the log |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
