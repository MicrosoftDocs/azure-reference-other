---
title: Azure Monitor Logs reference - AegPublishFailureLogs
description: Reference for AegPublishFailureLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 2/20/2020
---

# AegPublishFailureLogs

 AEG Event publish failure logs

## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|SourceSystem|string||
|TimeGenerated|datetime||
|Time|datetime|Time when log was generated.|
|SubResourceName|string|Name of the sub resource.|
|Category|string|Log category name.|
|OperationName|string|Name of the operation.|
|Message|string|Log message for the user.|
|Type|string||
|_ResourceId|string||
