---
title: Azure Monitor Logs reference - OEPAirFlowTask
description: Reference for OEPAirFlowTask table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
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
| Category | string | Logs generated as a result of operations executed using OAK APIs are grouped into categories. Categories in OAK are logical groupings based on the data source. |
| Content | string | Log details as a result of operation performed. |
| CorrelationId | string | Unique identifier to be used to correlate logs, when available. |
| DagTaskName | string | Name of Task executed in Airflow DAG. |
| Location | string | The region of the resource emitting the event. |
| OperationName | string | The operation name for which the log entry was created. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when the log was created. |
| Type | string | The name of the table |
