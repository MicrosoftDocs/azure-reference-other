---
title: Azure Monitor Logs reference - AMSMediaAccountHealth
description: Reference for AMSMediaAccountHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AMSMediaAccountHealth

 Media Account Health Status. This table captures the Azure Media Services account health status. It can be used to monitor account health status and diagnose issues for unhealthy accounts.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Media Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| EventCode | string | The event code. |
| EventMessage | string | The event status message. |
| Level | string | Log level of message, e.g. Informational. |
| Location | string | Location of the service sending the log. |
| OperationName | string | The name of the operation that triggered the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
