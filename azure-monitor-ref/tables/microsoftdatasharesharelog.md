---
title: Azure Monitor Logs reference - MicrosoftDataShareShareLog
description: Reference for MicrosoftDataShareShareLog table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# MicrosoftDataShareShareLog

 Microsoft Data Share Share Log

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The name of the log that belongs to |
| OperationName | string | The name of the operation represented by this event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log |
| Type | string | The name of the table |
