---
title: Azure Monitor Logs reference - ACSEmailSendMailOperational
description: Reference for ACSEmailSendMailOperational table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ACSEmailSendMailOperational

 Email Communication Services logs for send operations.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Communication Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AttachmentsCount | int | The count of attachments attached to a request. |
| BccRecipientsCount | int | The count of unique recipients on the 'Bcc' line. |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CcRecipientsCount | int | The count of unique recipients on the 'Cc' line. |
| CorrelationId | string | The ID for correlated events. This value is populated with the MessageID returned by Email send requests and can be used to identify correlated events between Email Operational tables. |
| Location | string | The location the request was processed. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Size | real | The size of the email in megabypes. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| ToRecipientsCount | int | The count of unique recipients on the 'To' line. |
| Type | string | The name of the table |
| UniqueRecipientsCount | int | The unique count of all recipients. |
