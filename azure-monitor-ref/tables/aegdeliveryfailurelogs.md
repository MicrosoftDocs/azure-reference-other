---
title: Azure Monitor Logs reference - AegDeliveryFailureLogs
description: Reference for AegDeliveryFailureLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# AegDeliveryFailureLogs

 Azure Event Grid - event delivery failure logs.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Event Grid Topics
- Event Grid Domains
- Event Grid Partner Topics
- Event Grid System Topics




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | Log category name. |
| EventSubscriptionName | string | Name of the event subscription. |
| Message | string | Log message for the user. |
| OperationName | string | Name of the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| SubResourceName | string | Name of the sub resource. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Time when log was generated. |
| Type | string | The name of the table |
