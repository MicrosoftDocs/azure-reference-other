---
ms.service: azure-monitor
ms.topic: include
ms.date: 04/15/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AZMSDiagnosticErrorLogs
---


| Column | Type | Description |
|---|---|---|
| ActivityId | string | A randomly generated UUID that ensures uniqueness for the audit activity. |
| ActivityName | string | Operation name. |
| _BilledSize | real | The record size in bytes |
| EntityName | string | Entity name. |
| EntityType | string | Entity type. |
| ErrorCount | int | Count of identical errors during the aggregation period of 1 minute. |
| ErrorMessage | string | Detailed error message. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NamespaceName | string | Namespace name. |
| OperationResult | string | Type of error (clienterror or serverbusy or quotaexceeded). |
| Provider | string | Event provider name. Possible values: eventhub, relay, and servicebus. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The event generation time (UTC). |
| Type | string | The name of the table |
