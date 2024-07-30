---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: DevCenterBillingEventLogs
---


| Column | Type | Description |
|---|---|---|
| BilledResourceId | string | The resource within the DevCenter that gets billed. |
| _BilledSize | real | The record size in bytes |
| BillingRegion | string | The billing region of the consomption resource. |
| EndTime | datetime | Time (UTC) when the consumption ended. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsOverMonthlyBillingCap | bool | Whether the consumption is included in the monthly cap. |
| MeterId | string | The meter ID for the consumption. |
| OperationName | string | The resource operation name for the log. |
| Quantity | real | The amount of usage in terms of the specified unit. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Sku | string | The Sku of the consumption resource. Can be DZH319G7LNXM, DZH3144F2XK5, DZH31814TZNG, etc. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | datetime | Time (UTC) when the consumption started. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time (UTC) when the log was created. |
| Type | string | The name of the table |
| UnitType | string | The unit in which the type of usage is measured. Can be Hourly or Monthly. |
| UsageResourceName | string | The name of the consumption resource. |
| UsageResourceUniqueId | string | The unique ID of the consumption resource. |
| UsageType | string | The type of resource being consumed. |
| UserId | string | User ID consuming the resource. |
