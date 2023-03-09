---
title: Azure Monitor Logs reference - AmlRegistryWriteEventsLog
description: Reference for AmlRegistryWriteEventsLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/9/2023
---

# AmlRegistryWriteEventsLog

 Azure ML Registry Write events log. It keeps records of Write operations with registries data access (data plane), including user identity, asset name and version for each access event.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AssetName | string | AzureML Asset name associated with log record. |
| AssetVersion | string | AzureML Asset version associated with log record. |
| CorrelationId | string | The correlation ID associated with log record. |
| Labels | string | Labels associated with log record. |
| RegistryResourceId | string | ARM ResourceId of the registry that generated this log record. |
| RegistryTenantId | string | TenantId associated with log record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserName | string | User name who initialized the event. |
| UserObjectId | string | User AAD object ID who initialized the event. |
