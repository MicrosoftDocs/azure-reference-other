---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: HDInsightHiveTezAppStats
---


| Column | Type | Description |
|---|---|---|
| AMContainerLogs | string | The Application Master? container logs. |
| ApplicationId | string | The ID of the Application that the metrics describe. |
| ApplicationName | string | The name of the application that the metrics describe. |
| ApplicationType | string | The type of application. |
| _BilledSize | real | The record size in bytes |
| ClusterId | long | The final status of the application if it has reached a terminal state. |
| ClusterName | string | Name of cluster. |
| ClusterType | string | Name of cluster. |
| CorrelationId | string | The ID for correlated events. Can be used to identify correlated events between multiple tables. |
| ElapsedTime | long | The time elapsed while the application was running. |
| FinalStatus | string | The final status of the application if it has reached a terminal state. |
| FinishedTime | long | The time the application finished. |
| HostName | string | Name of host where log was emitted. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LogAggregationStatus | string | The log aggregation status. |
| MetricName | string | Name of the metric for the record (e.g. AppsCompleted, AppsKilled, AppsFailed , etc). |
| MetricValue | real | Value of metric in the record. |
| OperationName | string | The operation associated with log record. |
| Queue | string | The queue of the application. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartedTime | long | The time the application started. |
| State | string | The state of the application. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| Tags | dynamic | Information about the record. For example a record may be tagged with 'yarn' if it is in the yarn context. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| TrackingUI | string | ?. |
| Type | string | The name of the table |
| UnmanagedApplication | bool | True if application is unmanaged, false if otherwise. |
| User | string | The name of the user of the application. |
