---
title: Azure Monitor Logs reference - ASRJobs
description: Reference for ASRJobs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# ASRJobs

This table contains records of Azure Site Recovery (ASR) jobs such as failover, test failover, reprotection etc., with key details for monitoring and diagnostics, such as the replicated item information, duration, status, description and so on. Whenever an ASR job is completed (i.e., succeeded or failed), a corresponding record for the job is sent to this table. You can view history of ASR jobs by querying this table over a larger time range, provided your workspace has the required retention configured.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.recoveryservices/vaults|
|**Categories**|Audit|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/asrjobs)|



## Columns
  
[!INCLUDE [asrjobs](.././tables/includes/asrjobs-include.md)]
