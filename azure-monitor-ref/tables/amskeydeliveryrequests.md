---
title: Azure Monitor Logs reference - AMSKeyDeliveryRequests
description: Reference for AMSKeyDeliveryRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/8/2022
---

# AMSKeyDeliveryRequests

 Key delivery requests logs from Azure Media Services. This table captures details for every HTTP request for key or license acquisition sent to Azure Media Services. It can be used to monitor encrypted content playback, and to diagnose issues with DRM license acquisition or Clear Key acquisition.

## Categories

- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- Media Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| DurationMs | int | Azure Media Services operation duration in milli-seconds. |
| KeyId | string | The ID of the requested key. |
| KeyType | string | Could be one of the following values: Clear (no encryption), FairPlay, PlayReady, or Widevine. |
| Level | string | Log level of message, e.g. Informational. |
| Location | string | Location of the service sending the log. |
| OperationName | string | The name of the operation that triggered the event. |
| OperationVersion | string | Azure Media Services operation version. |
| PolicyName | string | The Azure Resource Manager name of the policy. |
| RequestId | string | Id of the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | Azure Media Services operation result signature. |
| ResultType | string | Azure Media Services operation result type. |
| SourceSystem | string |  |
| StatusMessage | string | The status message. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| TokenType | string | The token type. |
| Type | string | The name of the table |
