---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AVNMNetworkGroupMembershipChange
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The correlation ID associated with the network group membership change operation of network resources. |
| DetailedMessage | string | A descriptive message that can include explanations and resolution steps in the case of failures or warnings. |
| GroupMemberships | dynamic | Details about the Virtual Network's membership of Network Group(s), including the networkgroupId, membership type, and membership details and IDs. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | Region of the Virtual Network. |
| LogLevel | string | Indicates the log level and can include: Info, Warning, Error. |
| Message | string | A brief success or failure message. |
| NetworkResourceIds | dynamic | Virtual Network IDs for which network group membership changed |
| OperationName | string |  Name of the operation that triggered the Virtual Network's addition or removal from a Network Group. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Indicates the operation status and can include: Success, Failure. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  The date and time the event was generated. |
| Type | string | The name of the table |
