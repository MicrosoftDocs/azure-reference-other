---
title: Azure Monitor Logs reference - AegDeliveryFailureLogs
description: Reference for AegDeliveryFailureLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# AegDeliveryFailureLogs

 AEG Event delivery failure logs

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Event Grid domain




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime||
|Time|datetime|Time when log was generated.|
|SubResourceName|string|Name of the sub resource.|
|EventSubscriptionName|string|Name of the event subscription.|
|Category|string|Log category name.|
|OperationName|string|Name of the operation.|
|Message|string|Log message for the user.|
|Type|string||
|_ResourceId|string||
