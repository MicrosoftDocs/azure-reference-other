---
title: Azure Monitor Logs reference - AMSStreamingEndpointRequests
description: Reference for AMSStreamingEndpointRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# AMSStreamingEndpointRequests

 Contains information about requests to streaming endpoints. A streaming endpoint receives HTTP requests needed to stream video content. These requests usually come from video players or from the CDN.

## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientIP | string | IP address of the client. |
| Level | string | Message level. Possible values are Informational, Warning, Error, Critical and Verbose. |
| Location | string | Location of the service sending the event. |
| OperationName | string | The name of the operation that triggered the event. |
| OperationVersion | string | Azure Media Services operation version. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| Status | string | Status code of the request. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) when the event was generated. |
| Type | string | The name of the table |
| URL | string | The streaming URL from Azure Media Services. |
