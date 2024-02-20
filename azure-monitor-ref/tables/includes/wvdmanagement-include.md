---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: WVDManagement
---


| Column | Type | Description |
|---|---|---|
| ArmObjectScope | string | The ARM object scope for the management request - used for session hosts, applications. |
| _BilledSize | real | The record size in bytes |
| ClientSideIPAddress | string | The remote IP address from the client side. |
| CorrelationId | string | The activity Id. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ObjectsCreated | int | The number of objects that were created. |
| ObjectsDeleted | int | The number of objects that were deleted. |
| ObjectsFetched | int | The number of objects that were fetched. |
| ObjectsUpdated | int | The number of objects that were updated. |
| ProvisioningCorrelationId | string | The ID of the top-level provisioning operation. This maps to the field in WVDSessionHostManagement table called CorrelationId. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Route | string | The route for the management request. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
| UserName | string | The user that initiated the management request. |
