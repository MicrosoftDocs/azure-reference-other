---
title: Azure Monitor Logs reference - SentinelHealth
description: Reference for SentinelHealth table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
---

# SentinelHealth

 Audit logs for operations performed by Azure Sentinel resources such as Data Connectors, Analytic Rules and more. These logs can be used to monitor the health of your Sentinel resources.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real | The record size in bytes |
| Description | string | The operation description. |
| ExtendedProperties | dynamic | Additional information based on the resource type. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| OperationName | string | The name of the operation that triggered the event. |
| Reason | string | The operation reason. |
| RecordId | string | A unique record identifier. |
| SentinelResourceId | string | The Sentinel resource ID. |
| SentinelResourceKind | string | The resource kind, for example: connector kind (such as Office365, AmazonWebServicesCloudTrail), alert rule kind (scheduld). |
| SentinelResourceName | string | The Sentinel resource name. |
| SentinelResourceType | string | The resource type, for example: DataConnector, AlertRule, etc. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Status | string | Status of the operation, for example: Success, Failure, Warning, Informational, Partial Success. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| Type | string | The name of the table |
| WorkspaceId | string | The workspace ID. |
