---
title: Azure Monitor Logs reference - AZKVPolicyEvaluationDetailsLogs
description: Reference for AZKVPolicyEvaluationDetailsLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/19/2023
---

# AZKVPolicyEvaluationDetailsLogs

 Contains details of Azure Policy Evaluation including the outcome and details of what checks were performed.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Key Vaults




## Columns

| Column | Type | Description |
| --- | --- | --- |
| DurationMs | int | Time it took to service the REST API request, in milliseconds. This does not include the network latency, so the time you measure on the client side might not match this time. |
| EvaluationDetails | dynamic | Details of Evaluation |
| IsComplianceCheck | bool | Is Compliance check enabled. |
| ObjectName | string | Name of the Object |
| ObjectType | string | Type of Object |
| OperationName | string | Name of the operation |
| Properties | dynamic | Information that varies based on the operation (operationName). In most cases, this field contains client information (the user agent string passed by the client), the exact REST API request URI, and the HTTP status code. In addition, when an object is returned as a result of a request (for example, KeyCreate or VaultGet), it also contains the key URI (as id), vault URI, or secret URI. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional description about the result, when available. |
| ResultSignature | string | HTTP status of the Request/Response |
| ResultType | string | Result of the REST API request. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when operation occured. |
| Type | string | The name of the table |
