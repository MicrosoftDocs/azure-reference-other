---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AmlPipelineEvent
---


| Column | Type | Description |
|---|---|---|
| AadTenantId | string | The AAD tenant ID the operation was submitted for. |
| AmlModuleId | string | The unique ID of the module. |
| AmlModuleName | string | The name of the AML Module. |
| AmlParentPipelineId | string | The ID of the parent AML pipeline (in the case of cloning). |
| AmlPipelineDraftId | string | The ID of the AML pipeline draft. |
| AmlPipelineDraftName | string | The name of the AML pipeline draft. |
| AmlPipelineEndpointId | string | The ID of the AML pipeline endpoint. |
| AmlPipelineEndpointName | string | The name of the AML pipeline endpoint. |
| AmlPipelineId | string | The ID of the AML pipeline. |
| AmlWorkspaceId | string | The unique ID of the AML workspace. |
| AmlWorkspaceName | string | The name of the AML workspace. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | A GUID used to group together a set of related events. |
| Identity | dynamic | The identity of the user or application that performed the operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The name of the operation associated with the log entry. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | The status of the event. Typical values include Started, In Progress, Succeeded, Failed, Active, and Resolved. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| Type | string | The name of the table |
