---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AVNMRuleCollectionChange
---


| Column | Type | Description |
|---|---|---|
| AppliedRuleCollectionIds | dynamic | List of current applied rule collections to the network resources like virtual networks or subnets listed in TargetResourceIds by your network manager. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The correlation ID associated with the rule collection change operation of network resources. Logs having same correlation Ids are part of same rule collection change operation. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | Region of the network resource managed by network manager like virtual network, subnets. |
| LogLevel | string | Indicates the log level and can include: Info, Warning, Error. |
| Message | string | A brief success or failure message. |
| NetworkResourceIds | dynamic | Virtual Network or Subnet IDs for which applied rule collections changed |
| OperationName | string |  Name of the operation that applies rule collections or removes applied rule collections on network resources like virtual network, subnets. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultType | string | Indicates the operation status and can include: Success, Failure. |
| SelfDiagnosis | string | A descriptive self diagnosis message that can include explanations and resolution steps in the case of failures or warnings. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |  The date and time the event was generated. |
| Type | string | The name of the table |
