---
title: Azure Monitor Logs reference - GCPAuditLogs
description: Reference for GCPAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# GCPAuditLogs

The Google Cloud Platform (GCP) audit logs, ingested from Sentinel's connector, enable you to capture three types of audit logs: admin activity logs, data access logs, and access transparency logs. Google cloud audit Logs record a trail that practitioners can use to monitor access and detect potential threats across Google Cloud Platform (GCP) resources.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|Security|
|**Solutions**| SecurityInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/gcpauditlogs)|



## Columns
  
[!INCLUDE [gcpauditlogs](./includes/gcpauditlogs-include.md)]
