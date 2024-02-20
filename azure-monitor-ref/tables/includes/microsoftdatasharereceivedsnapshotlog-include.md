---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MicrosoftDataShareReceivedSnapshotLog
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string | The name of the log that belongs to |
| CorrelationId | string | CorrelationId of the event, this can be use as a reference to join with other tables |
| DataSetMappingType | string | Indicating the dataSetMapping type, this can be Blob/container/bolbfolder,etc |
| DataSetName | string | Name of provider source dataset |
| DataSetType | string | Indicating the dataSet type, this can be Blob/container/bolbfolder,etc |
| DetailMessage | string | This shows the event details. Can be empty if synchronization is not finished |
| EndTime | string | Datashare synchronization end time, can be empty if job not finished |
| FilesRead | string | Number of files read from source |
| FilesWritten | string | Number of files written into sink |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string | The name of the operation represented by this event |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SizeRead | string | Size of files read from source |
| SizeWritten | string | Size of files into sink in bytes |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StartTime | string | Datashare synchronization start time |
| Status | string | Synchronization status, can be inprogress/succeed/failed |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The time (UTC) when the event is generated |
| TriggerType | string | Indicating whether the trigger is on-demand trigger or manual trigger |
| Type | string | The name of the table |
