---
title: Azure Monitor Logs reference - DCRLogTroubleshooting
description: Reference for DCRLogTroubleshooting table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# DCRLogTroubleshooting

Logs from DCR-based data collection and transformation to help with troubleshooting of DCR configuration and flow.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Data Collection Rules




## Columns

| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| ClientRequestId | string | Guid passed in x-ms-client-request-id header while ingesting data. |
| CorrelationId | string | The ID for the correlated events. Can be used to identify correlated events between multiple tables. |
| InputStreamId | string | Stream name of the input. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Message | string | Error describing the issue. |
| OperationName | string | Name of the operation, Can be Ingestion or Transformation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
