---
title: Azure Monitor Logs reference - CDBPartitionKeyRUConsumption
description: Reference for CDBPartitionKeyRUConsumption table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# CDBPartitionKeyRUConsumption

This table details the RU (Request Unit) consumption for logical partition keys in each region, within each of their physical partitions. This data can be used to identify hot partitions from a request volume perspective.


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
  
[!INCLUDE [cdbpartitionkeyruconsumption](.././tables/includes/cdbpartitionkeyruconsumption-include.md)]
