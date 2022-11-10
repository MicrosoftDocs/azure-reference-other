---
title: Azure Monitor Logs reference - ADFAirflowSchedulerLogs
description: Reference for ADFAirflowSchedulerLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ADFAirflowSchedulerLogs

 ADF Airflow scheduler logs

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The category of the log that belongs to Airflow application. |
| CorrelationId | string | The correlation id of the event. |
| DataFactoryName | string | The name of the Data factory. |
| IntegrationRuntimeName | string | The name of the Integration runtime. |
| Message | string | The application log of the Airflow event. |
| OperationName | string | The name of the operation represented by this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of the log. |
| Type | string | The name of the table |
