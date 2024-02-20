---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: CHSMManagementAuditLogs
---


| Column | Type | Description |
|---|---|---|
| AdditionalFields | dynamic | Information that varies based on the operation (operationName). This field provides additional information about the operation performed on a particular HSM partition. |
| _BilledSize | real | The record size in bytes |
| CommandType | string | The type of command in hexadecimal format. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | Location of the CloudHsm resource. |
| LogType | string | The type of the log entry. |
| MemberId | string | HSM partition identifier to whom this particular audit log belong. |
| Opcode | string | Opcode that is used to describe the HSM operation performed. |
| OperationId | string | A GUID to correlate with service side logs. |
| OperationName | string | Name of the operation. |
| RebootCounter | string | This is a persistent counter that gets incremented on every reboot of the HSM. This number never gets reset to '0'. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Response | string | The result of HSM operation performed. |
| SchemaVersion | string | Service side schema version. |
| SequenceNo | string | This is a volatile counter that gets incremented when logging every loggable command. On every reboot of the HSM or when the partition gets destroyed, the sequence number resets to zero. |
| SessionHandle | string | A hexadecimal number that represents the session handle. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when operation occured. |
| Type | string | The name of the table |
| UserId | string | User identification. |
| Version | string | Version number for HSM operation log. |
