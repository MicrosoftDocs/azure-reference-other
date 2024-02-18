---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AZMSRunTimeAuditLogs
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | A randomly generated UUID that ensures uniqueness for the audit activity. |
| ActivityName | string | Runtime operation name. |
| AuthKey | string | Azure Active Directory application ID or SAS policy name that's used to authenticate to a resource. |
| AuthType | string | Type of authentication (Azure Active Directory or SAS Policy). |
| _BilledSize | real | The record size in bytes |
| ClientIp | string | IP address of the client application. |
| Count | int | Total number of operations performed during the aggregated period of 1 minute. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NetworkType | string | Type of the network access: Public or Private. |
| Properties | dynamic | Metadata that are specific to the data plane operation. |
| Protocol | string | Type of the protocol associated with the operation. |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Status of the activity (success or failure). |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| Type | string | The name of the table |
