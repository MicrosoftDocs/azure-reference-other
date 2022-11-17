---
title: Azure Monitor Logs reference - HDInsightGatewayAuditLogs
description: Reference for HDInsightGatewayAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# HDInsightGatewayAuditLogs

 Authentication audit logs from HDInsight Gateway nodes.

## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccessRequestCount | real | Number of login requests associated with the user. |
| ClusterDnsName | string | The DNS name of the cluster. |
| ErrorMessage | string | Any error message associated with the login attempt. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Status | string | The outcome of the login attempt. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserName | string | The username used for the login attempt. |
