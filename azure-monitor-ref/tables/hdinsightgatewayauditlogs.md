---
title: Azure Monitor Logs reference - HDInsightGatewayAuditLogs
description: Reference for HDInsightGatewayAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# HDInsightGatewayAuditLogs

 Authentication audit logs from HDInsight Gateway nodes.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- HDInsight Clusters




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccessRequestCount | real | Number of login requests associated with the user. |
| _BilledSize | real |  |
| ClusterDnsName | string | The DNS name of the cluster. |
| ErrorMessage | string | Any error message associated with the login attempt. |
| _IsBillable | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| Status | string | The outcome of the login attempt. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The timestamp (UTC) of when the log was generated. |
| Type | string | The name of the table |
| UserName | string | The username used for the login attempt. |
