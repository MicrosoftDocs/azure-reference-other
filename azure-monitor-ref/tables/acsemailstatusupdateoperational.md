---
title: Azure Monitor Logs reference - ACSEmailStatusUpdateOperational
description: Reference for ACSEmailStatusUpdateOperational table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/17/2023
---

# ACSEmailStatusUpdateOperational

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
| _BilledSize | real | The record size in bytes |
| Category | string | The log category of the event. Logs with the same log category and resource type will have the same properties fields. |
| CorrelationId | string | The ID for correlated events. This value is populated with the MessageID returned by Email send requests and can be used to identify correlated events between Email Operational tables. |
| DeliveryStatus | string | The count of unique recipients on the Cc line. |
| EnhancedSmtpStatusCode | string | The enhanced SMTP status code returned from the recipient email server (if available). |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| IsHardBounce | string | Signifies whether a delivery failure was due to a permanent or temporary issue. IsHardBounce == true means a permanent mailbox issue preventing emails from being delivered. |
| Location | string | The location the request was processed. |
| OperationName | string | The operation associated with log record. |
| OperationVersion | string | The API-version associated with the operation or version of the operation (if there is no API version). |
| RecipientId | string | The count of unique recipients on the To line. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SenderDomain | string | The domain portion of the SenderAddress used in sending emails. |
| SenderUsername | string | The username portion of the SenderAddress used in sending emails. |
| SmtpStatusCode | string | The SMTP status code returned from the recipient email server in response to  a send  mail request. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
