---
title: Azure Monitor Logs reference - CDBDataPlaneRequests
description: Reference for CDBDataPlaneRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# CDBDataPlaneRequests

The DataPlaneRequests table captures every data plane operation for the Cosmos DB account. Data Plane requests are operations executed to create, update, delete or retrieve data within the account.


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
  
[!INCLUDE [cdbdataplanerequests](.././tables/includes/cdbdataplanerequests-include.md)]
