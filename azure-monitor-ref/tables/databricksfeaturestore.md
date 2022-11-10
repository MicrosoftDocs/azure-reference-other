---
title: Azure Monitor Logs reference - DatabricksFeatureStore
description: Reference for DatabricksFeatureStore table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# DatabricksFeatureStore

 Audit logs for events related to Databricks ML Feature Store operations.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Databricks Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionName | string | The action of the request. |
| Category | string | The service that logged the request. |
| Identity | string | Information about the user that makes the requests. |
| LogId | string | The unique identifier for the log message that can be used to deduplicate them. |
| OperationName | string | The action, such as login, logout, read, write, etc. |
| OperationVersion | string | The schema version of the Databricks operation-based diagnostic log format. |
| RequestId | string | The unique request ID. |
| RequestParams | string | Parameter key-value pairs used in the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Response | string | The HTTP response to the request, including error message (if applicable), result, and statusCode. |
| ServiceName | string | The service of the source request. |
| SessionId | string | Session ID of the action. |
| SourceIPAddress | string | The IP address of the source request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp of the action (UTC). |
| Type | string | The name of the table |
| UserAgent | string | The browser or API client used to make the request. |
