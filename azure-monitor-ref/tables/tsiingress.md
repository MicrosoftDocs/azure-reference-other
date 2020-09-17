---
title: Azure Monitor Logs reference - TSIIngress
description: Reference for TSIIngress table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# TSIIngress

 The Ingress category tracks errors that occur in the ingress pipeline. This category includes errors that occur when receiving events (such as unable to connect to the Event Source), processing events (such as unable to parse the event payload), and writing to storage (such as unauthorized when trying to access the storage account).

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Time Series Insights Environments




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|Category of the log event.|
|Error|dynamic|Elaborate description of the error. Contains information such as faulting components, etc.|
|Level|string|The severity level of the event.|
|OperationName|string|Operation name of the event.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResultDescription|string|Description of the operation, such as 'Received forbidden error'.|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|Time at which this event is generated.|
|Type|string|The name of the table|
