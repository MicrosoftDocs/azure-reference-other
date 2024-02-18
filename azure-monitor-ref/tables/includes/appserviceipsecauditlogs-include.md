---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AppServiceIPSecAuditLogs
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CIp | string | IP address of the client |
| CsHost | string | Host header of the HTTP request |
| Details | string | Additional information |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string | The result whether the access is Allowed or Denied |
| ServiceEndpoint | string | This indicates whether the access is via Virtual Network Service Endpoint communication |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Time of the Http Request |
| Type | string | The name of the table |
| XAzureFDID | string | X-Azure-FDID header (Azure Frontdoor Id) of the HTTP request |
| XFDHealthProbe | string | X-FD-HealthProbe (Azure Frontdoor Health Probe) of the HTTP request |
| XForwardedFor | string | X-Forwarded-For header of the HTTP request |
| XForwardedHost | string | X-Forwarded-Host header of the HTTP request |
