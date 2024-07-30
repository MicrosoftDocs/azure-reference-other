---
title: Azure Monitor Logs reference - CDBQueryRuntimeStatistics
description: Reference for CDBQueryRuntimeStatistics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
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
  
[!INCLUDE [cdbqueryruntimestatistics](./includes/cdbqueryruntimestatistics-include.md)]
