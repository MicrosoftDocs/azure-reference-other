---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MicrosoftAzureBastionAuditLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientIpAddress | string | Browser IP Address that was used to log into the VirtualMachine from Bastion |
| ClientPort | int | Browser Port Number that was used to log into the VirtualMachine from Bastion |
| Duration | int | Duration in milliseconds where the Bastion Session lasted (available only when the Bastion Session ended) |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The location of the server that processed the request (e.g., South Central US). |
| Message | string | Additonal text that's assoicated of this event |
| OperationName | string | The name of the operation represented by this event |
| Protocol | string | Protocol (could be ssh or rdp) that was used to log into the VirtualMachine from Bastion |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceType | string | Resource Type that was accessed during the session. This could be a VM/VMSS/BSL/etc. |
| SessionEndTime | string | Timestamp (UTC) of when the Bastion Session was ended |
| SessionStartTime | datetime | Timestamp (UTC) of when the Bastion Session was started |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TargetResourceId | string | ResourceID of the VirtualMachine where the Bastion was connected to |
| TargetVMIPAddress | string | IP Address of VirtualMachine where the Bastion was connected to |
| TenantId | string | The Log Analytics workspace ID |
| Time | datetime | The timestamp (UTC) of the log |
| TimeGenerated | datetime |   |
| TunnelId | string | Internal Bastion Connection GUID |
| Type | string | The name of the table |
| UserAgent | string | Browser User Agent that the request was sent |
| UserEmail | string | UserEmail account that was used to log into the VirtualMachine |
| UserName | string | UserName that was used to log into the VirtualMachine from Bastion |
