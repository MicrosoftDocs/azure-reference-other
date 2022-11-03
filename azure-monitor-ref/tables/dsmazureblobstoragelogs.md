---
title: Azure Monitor Logs reference - DSMAzureBlobStorageLogs
description: Reference for DSMAzureBlobStorageLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# DSMAzureBlobStorageLogs

 Azure Blob Storage resource logs enriched with data sensitivity context provided by Azure Purview.

## Categories

- Security
- Azure Resources
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountName | string | The name of the storage account. |
| AggregationCount | long | Number of events that were aggregated into a single entry. |
| AggregationLastEventTime | datetime | The time (UTC) when the last request was received by storage. |
| AuthenticationHash | string | The hash of authentication token. |
| AuthenticationType | string | The type of authentication that was used to make the request. E.g. OAuth, SAS, etc. |
| CallerIpAddress | string | The IP address of the requester. |
| Category | string | The category of requested operation. |
| CorrelationId | string | The ID that is used to correlate resource logs with data sensitivity logs. |
| Location | string | The location of storage account. |
| OperationName | string | The type of REST operation that was performed. For example: GetBlob, DeleteBlob. |
| RequesterAppId | string | The Open Authorization (OAuth) application ID that is used as the requester. |
| RequesterObjectId | string | The Open Authorization (OAuth) object ID that is used as the requester. |
| RequesterTenantId | string | The Open Authorization (OAuth) tenant ID that is used as the requester. |
| RequesterUpn | string | The user principal names (UPN) of requestor. |
| ResourceGroup | string | The Resource Group name of the storage account that was accessed. |
| ResourceSubscriptionId | string | The subscription ID (GUID) of the storage account being accessed. |
| SourceSystem | string |  |
| StatusCode | string | The HTTP status code for the request. If the request is interrupted, this value might be set to Unknown. |
| SumResponseBodySize | long | The sum of packets in responses written by the storage service, in bytes. If request(s) are unsuccessful, this value may be empty. |
| TenantId | string |  |
| TimeGenerated | datetime | The time (UTC) when the first request was received by storage. |
| Type | string | The name of the table |
| Uri | string | Uniform resource identifier that is requested. |
| UserAgentHeader | string | The user-agent header value. |
