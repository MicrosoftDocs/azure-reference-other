---
title: Azure Monitor Logs reference - DatabricksWorkspaceLogs
description: Reference for DatabricksWorkspaceLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: orens
author: osalzberg
ms.date: 07/30/2024
---

# DatabricksWorkspaceLogs

Schema for Databricks workspaces related categories, this is an umbrella schema to hold all new Databricks Audit Logs categories that happened in the workspace beginning from 2024. Legacy categories before 2024 are held in their own schemas.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|-|
|**Solutions**| LogManagement|
|**Basic log**|No|
|**Ingestion-time transformation**|No|
|**Sample Queries**|[Yes](/azure/azure-monitor/reference/queries/databricksworkspacelogs)|



## Columns
  
[!INCLUDE [databricksworkspacelogs](./includes/databricksworkspacelogs-include.md)]
