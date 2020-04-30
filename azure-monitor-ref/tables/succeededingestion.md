---
title: Azure Monitor Logs reference - SucceededIngestion
description: Reference for SucceededIngestion table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# SucceededIngestion

 Succeeded ingestion operations

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Data Explorer cluster




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string|The category of this log|
|CorrelationId|string|The ingestion source id|
|Database|string|The name of the database holding the target table|
|IngestionSourceId|string|A unique identifier representing the ingested source|
|IngestionSourcePath|string|The Azure blob storage URI|
|OperationId|string|The ingestion's operation Id|
|OperationName|string|The name of this operation|
|OperationVersion|string|The version of this event|
|_ResourceId|string||
|ResultType|string|The final state of this data ingestion operation|
|RootActivityId|string|The ingestion's activity Id|
|SourceSystem|string||
|SucceededOn|datetime|Time at which this ingest operation successfully ended|
|Table|string|The name of the target table into which the data is ingested|
|TenantId|string||
|TimeGenerated|datetime|Time at which this event is generated and logged|
|Type|string||
