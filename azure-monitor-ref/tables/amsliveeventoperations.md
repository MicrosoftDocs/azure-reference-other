---
title: Azure Monitor Logs reference - AMSLiveEventOperations
description: Reference for AMSLiveEventOperations table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# AMSLiveEventOperations

 Contains logs related to a Live Event. Logs are sent when an encoder connects, disconnects, or if there is a discontinuity in the media data.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Level | string | Message level. Possible values are Informational, Warning, Error, Critical and Verbose. |
| Location | string | Location of the service sending the event. |
| OperationName | string | The name of the operation that triggered the event. |
| Properties | dynamic | Operation details. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the event was generated. |
| Type | string | The name of the table |
