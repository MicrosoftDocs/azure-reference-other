---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AADProvisioningLogs
---


| Column | Type | Description |
|---|---|---|
| AADTenantId | string | Unique Azure AD tenant ID |
| _BilledSize | real | The record size in bytes |
| Category | string | Category of the event |
| ChangeId | string | Unique ID of this change in this cycle |
| CorrelationId | string | ID to provide provisioning trail |
| CycleId | string | Unique ID per job iteration |
| DurationMs | long | Indicates how long this provisioning action took to finish |
| Id | string | Indicates the unique ID for the activity |
| InitiatedBy | string | Details of who initiated this provisioning |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| JobId | string | The unique ID for the whole provisioning job |
| ModifiedProperties | string | Details of each property that was modified in this provisioning action on this object |
| OperationName | string | Name of the operation |
| OperationVersion | string | The REST API version that's requested by the client |
| ProvisioningAction | string | Indicates the activity name or the operation name. For a list of activities logged, refer to Azure AD activity list |
| ProvisioningStatusInfo | string | Details of provisioning status |
| ProvisioningSteps | string | Details of each step in provisioning |
| ResultDescription | string | When available, provides the error description for the provisioning operation |
| ResultSignature | string | Contains the error code, if any, for the provisioning operation |
| ResultType | string | The result of the provisioning operation can be Success, Failure, or Skipped |
| ServicePrincipal | string | Represents the service principal used for provisioning |
| SourceIdentity | string | Details of source object being provisioned |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TargetIdentity | string | Details of target object being provisioned |
| TargetSystem | string | Details of target system of the object being provisioned |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time of the event in UTC |
| Type | string | The name of the table |
