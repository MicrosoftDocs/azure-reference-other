---
title: Azure Monitor Logs reference - CDBQueryRuntimeStatistics
description: Reference for CDBQueryRuntimeStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# CDBQueryRuntimeStatistics

This table details query operations executed against a SQL API account. By default, the query text and its parameters are obfuscated to avoid logging PII data with full text query logging available by request.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.documentdb/databaseaccounts|
|**Categories**|Azure Resources, Audit|
|**Solutions**| LogManagement|
|**Basic log**|Yes|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [cdbqueryruntimestatistics](.././tables/includes/cdbqueryruntimestatistics-include.md)]
