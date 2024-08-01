---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: WVDSessionHostManagement
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientType | string | Information about the client that initiated the update (portal, Powershell etc.). |
| CorrelationId | string | The correlation ID for the activity. |
| FailedSessionHostCleanupPolicy | string | The policy for cleaning up session hosts that have failed provisioning. |
| FromInstanceCount | int | The instance count before the operation. For an update operation, FromInstanceCount and ToInstanceCount are the same value. |
| FromSessionHostConfigVer | string | The version of SHC before the operation (that session hosts are moving from; can be looked up with new SHC table). For a provisioning operation, it is the same as the ToSessionHostConfiguration. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| ProvisioningCanaryPolicy | string | The policy for creating a test canary session host before creating the rest of the requested session hosts. |
| ProvisioningStatus | string | The status of the current update/provisioning operation. |
| ProvisioningType | string | The type of operation (provisioning, update). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ScheduledDateTime | string | When the session host update is scheduled, the scheduled time. |
| ScheduledDateTimeZone | string | The time zone that updates and provisioning happen in. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of the event. |
| ToInstanceCount | int | The instance count after the operation. For an update operation, FromInstanceCount and ToInstanceCount are the same value. |
| ToSessionHostConfigVer | string | The version of SHC after the operation (that session hosts are moving to; can be looked up with new SHC table). For a provisioning operation, is the same as the FromSessionHostConfiguration is. |
| Type | string | The name of the table |
| UpdateDeleteOriginalVm | bool | Property indicates whether the original VM should be deleted after the update. |
| UpdateMaxVmsRemoved | int | The maximum number of virtual machines that might become unavailable during the session host update operation. |
| UpdateMethod | string | The method that is used for the session host update operation (e.g.: VmRecreate). |
| UpdateStartWindowInMinutes | int | The window of allowable time for an update to start in minutes. |
