---
title: Azure Monitor Logs reference - OEPAirFlowTask
description: Reference for OEPAirFlowTask table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/19/2023
---

# OEPAirFlowTask

 Diagnostic logs for AirFlow task execution having task name, task details.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Microsoft.OpenEnergyPlatform/energyServices




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AdditionalLogContent | string | Additional log content, if there is any more info that needs to be populated |
| Category | string | Logs generated as a result of operations executed using OAK APIs are grouped into categories. Categories in OAK are logical groupings based on the data source. |
| CodePath | string | The task inside the DAG run which generated the log |
| Content | string | Log details as a result of operation performed. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| DagName | string | Name of the DAG run - as per Airflow's list of DAGs present |
| DagTaskName | string | Name of Task executed in Airflow DAG. |
| Location | string | The region of the resource emitting the event. |
| LogLevel | string | Log Level of the log - Info/Debug/Warning/Error |
| OperationName | string | The operation name for which the log entry was created. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RunId | string | To identify the particular DAG run which generated the log |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| TryNumber | string | Still not available |
| Type | string | The name of the table |
