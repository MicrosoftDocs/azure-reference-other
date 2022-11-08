---
title: Azure Monitor Logs reference - ACSEmailUserEngagementOperational
description: Reference for ACSEmailUserEngagementOperational table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# ACSEmailUserEngagementOperational

 Email Communication Services logs for message and recipient depllivery status update operations.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. This value is populated with the MessageID returned by Email send requests and can be used to identify correlated events between Email Operational tables. |
| EngagementContext | string | The context of the user interaction. |
| EngagementType | string | The type of user engagement. |
| Location | string | The location the request was processed. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| RecipientId | string | The count of unique recipients on the To line. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserAgent | string | The user agent string of the client application. |
