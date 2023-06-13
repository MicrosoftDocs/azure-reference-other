---
title: Azure Monitor Logs reference - AppServiceIPSecAuditLogs
description: Reference for AppServiceIPSecAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AppServiceIPSecAuditLogs

 Logs generated through your application and pushed to Azure Monitoring.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| CIp | string | IP address of the client |
| CsHost | string | Host header of the HTTP request |
| Details | string | Additional information |
| _IsBillable | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string | The result whether the access is Allowed or Denied |
| ServiceEndpoint | string | This indicates whether the access is via Virtual Network Service Endpoint communication |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time of the Http Request |
| Type | string | The name of the table |
| XAzureFDID | string | X-Azure-FDID header (Azure Frontdoor Id) of the HTTP request |
| XFDHealthProbe | string | X-FD-HealthProbe (Azure Frontdoor Health Probe) of the HTTP request |
| XForwardedFor | string | X-Forwarded-For header of the HTTP request |
| XForwardedHost | string | X-Forwarded-Host header of the HTTP request |
