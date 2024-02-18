---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightAmbariClusterAlerts
---


| Column | Type | Description |
|---|---|---|
| AlertFirmness | string | The firmness of the alert. |
| AlertID | int | The ID of the alert message. |
| AlertInstance | string | Instance number of the alert. |
| _BilledSize | real | The record size in bytes |
| ClusterName | string | The name of the cluster the alert came from. |
| ClusterType | string | The type of cluster where the alert was generated. |
| ComponentName | string | The component that generated the alert. |
| DefinitionId | int | Id of the alert definition. |
| DefinitionName | string | Name of the alert definition |
| HostFQDN | string | The FQDN of the host where the alert was generated. |
| HostName | string | The name of the host where the alert was generated. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Label | string | The label of the alert. |
| LatestTimestamp | long | The latest time the alert occurred. |
| MaintenanceState | string | The maintenance classifaction state of the alert. |
| Occurences | int | The number of times an alert has occurred. |
| OriginalTimestamp | long | The timestamp the alert first occurred. |
| ReferenceURI | string | The URI to the alert. |
| RepeatTolerance | int | The total number of occurences an alert can have before being escalated. |
| RepeatToleranceRemaining | int | The amount of occurences left before an alert gets escalted. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Scope | string | The scope of the alert. |
| ServiceName | string | The name of the service that generated the alert. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| State | string | The state of the alert. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| Text | string | The informational text of the alert. |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
