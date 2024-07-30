---
title: Azure Monitor Logs reference - ASRReplicatedItems
description: Reference for ASRReplicatedItems table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# ASRReplicatedItems

This table contains details of Azure Site Recovery (ASR) replicated items, such as associated vault, policy, replication health, failover readiness. etc. Data is pushed once a day to this table for all replicated items, to provide the latest information for each item.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|microsoft.recoveryservices/vaults|
|**Categories**|Audit|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/asrreplicateditems)|



## Columns
  
[!INCLUDE [asrreplicateditems](./includes/asrreplicateditems-include.md)]
