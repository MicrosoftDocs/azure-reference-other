---
title: Azure Monitor Logs reference - SynapseBigDataPoolApplicationsEnded
description: Reference for SynapseBigDataPoolApplicationsEnded table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# SynapseBigDataPoolApplicationsEnded

 Information about ended Apache Spark applications.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Synapse Workspaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Category | string | The category of the log. |
| CorrelationId | string | A GUID used to group together a set of related events. |
| Identity | dynamic | A JSON blob that describes the identity of the user or application that performed the operation. |
| OperationName | string | The operation associated with log record. |
| Properties | dynamic | extended properties related to this event. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
