---
title: Azure Monitor Logs reference - ADFSSISPackageEventMessages
description: Reference for ADFSSISPackageEventMessages table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# ADFSSISPackageEventMessages

 ADF SSIS package execution event messages

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
| EventMessageGuid | string | Event message guid |
| EventName | string | Event name |
| ExecutionPath | string | Execution path |
| ExtendedInfoId | long | Extended info id |
| IntegrationRuntimeName | string | Integration runtime name |
| Level | string | Verbosity level of log |
| Message | string | Event message |
| MessageCode | int | Message code |
| MessageSourceId | string | Message source id |
| MessageSourceName | string | Message source name |
| MessageSourceType | int | Message source type |
| MessageTime | datetime | Message time |
| MessageType | int | Message type |
| OperationId | long | Operation id |
| OperationName | string | The name of the operation represented by this event |
| PackageName | string | Package name |
| PackagePath | string | Package path |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| SubcomponentName | string | Subcomponent name |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| ThreadId | int | Thread id |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
