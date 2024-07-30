---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: OEPAirFlowTask
---


| Column | Type | Description |
|---|---|---|
| AdditionalLogContent | string | Additional log content, if there is any more info that needs to be populated |
| _BilledSize | real | The record size in bytes |
| Category | string | Logs generated as a result of operations executed using OAK APIs are grouped into categories. Categories in OAK are logical groupings based on the data source. |
| CodePath | string | The task inside the DAG run which generated the log |
| Content | string | Log details as a result of operation performed. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| DagName | string | Name of the DAG run - as per Airflow's list of DAGs present |
| DagTaskName | string | Name of Task executed in Airflow DAG. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The region of the resource emitting the event. |
| LogLevel | string | Log Level of the log - Info/Debug/Warning/Error |
| OperationName | string | The operation name for which the log entry was created. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RunId | string | To identify the particular DAG run which generated the log |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| TryNumber | string | Still not available |
| Type | string | The name of the table |
