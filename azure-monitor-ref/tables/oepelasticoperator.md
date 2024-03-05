---
title: Azure Monitor Logs reference - OEPElasticOperator
description: Reference for OEPElasticOperator table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# OEPElasticOperator

Diagnostic logs for elastic operator. Elastic operator manages all the elasticsearch clusters in the oak instance. These logs can be helpful in identifing what operations are performed by the operator on the cluster. It could be upgrades, reconciliation, resource update etc.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.openenergyplatform/energyservices|
|**Categories**|Azure Resources|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [oepelasticoperator](.././tables/includes/oepelasticoperator-include.md)]
