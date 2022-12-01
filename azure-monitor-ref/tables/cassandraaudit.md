---
title: Azure Monitor Logs reference - CassandraAudit
description: Reference for CassandraAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# CassandraAudit

 Detailed audit records for CQL operations and login attempts.

## Categories

- Audit
## Solutions

- LogManagement
## Resource types

- Azure Managed Instance for Apache Cassandra




## Columns

| Column | Type | Description |
| --- | --- | --- |
| BatchId | string | Internal identifier shared by all statements in a batch operation. |
| ClientIP | string | Client IP address. |
| ClientPort | string | Client port. |
| ClusterName | string | Cluster name. |
| CoordinatorIP | string | Host address of the coordinator node. |
| ExternalUserId | string | External user identity. |
| Operation | string | The CQL statement or a textual description of the operation. |
| OperationNaked | string | The CQL statement or a textual description of the operation, without bound values appended to prepared statements. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Status | string | Value is either ATTEMPT or FAILED. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time the record was created. |
| Type | string | The name of the table |
| User | string | Username of the authenticated user. |
