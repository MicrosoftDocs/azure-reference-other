---
title: Azure Monitor Logs reference - DatabricksCapsule8Dataplane
description: Reference for DatabricksCapsule8Dataplane table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# DatabricksCapsule8Dataplane

 Audit logs for Databricks service capsule8-alerts-dataplane.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActionName | string | The action of the request. |
| Category | string | The service that logged the request. |
| Identity | dynamic | Information about the user that makes the requests. |
| LogId | string | The unique identifier for the log messages. |
| OperationName | string | The action, such as login, logout, read, write, etc. |
| OperationVersion | string | The Databricks schema version of the diagnostic log format. |
| RequestId | string | Unique request ID. |
| RequestParams | dynamic | Parameters, key-value pairs used in the event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Response | dynamic | The HTTP response to the request, including error message (if applicable), result, and status code. |
| ServiceName | string | The service of the source request. |
| SessionId | string | Session ID of the action. |
| SourceIPAddress | string | The IP address of the source request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp of the action (UTC). |
| Type | string | The name of the table |
| UserAgent | string | The browser or API client used to make the request. |
