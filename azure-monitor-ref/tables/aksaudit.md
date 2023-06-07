---
title: Azure Monitor Logs reference - AKSAudit
description: Reference for AKSAudit table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/1/2023
---

# AKSAudit

 Contains all Kubernetes API Server audit logs including events with the get and list verbs. These events are useful for monitoring all of the interactions with the Kubernetes API. To limit the scope to modifying operations see the AKSAuditAdmin table.

## Categories

- Audit
- Azure Resources
- Containers
## Solutions

- LogManagement
## Resource types

- Kubernetes Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Annotations | dynamic | An unstructed key-value map associated with this audit event. These annotations are set by plugins as part of the request serving chain and are included at the Metadata event level. |
| AuditId | string | Unique audit ID that is generated for each request. |
| _BilledSize | real |  |
| _IsBillable | string |  |
| Level | string | Level (Metadata, Request, RequestResponse) of the audit event. |
| ObjectRef | dynamic | The Kubernetes object reference this event was targeted for. This field does not apply for list requests nor non-resource requests. |
| PodName | string | Name of the pod emitting this audit event. |
| RequestObject | dynamic | Kubernetes API object from the request in object format or the string "skipped-too-big-size-object". This is omitted for non-resource requests. |
| RequestReceivedTime | datetime | Time when the API Server first received the request. |
| RequestUri | string | The URI of the request made by the client to the server. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponseObject | dynamic | Kubernetes API object from the response, in object format or the string "skipped-too-big-size-object". This is omitted for non-resource requests. |
| ResponseStatus | dynamic | Response status for the request, which includes the response code. In error cases, this object will include the error message property. |
| SourceIps | dynamic | The list of source IP addresses for the originating client and intermediate proxies. |
| SourceSystem | string |  |
| Stage | string | The request handling stage (RequestReceived, ResponseStarted, ResponseComplete, Panic) at which this audit event was generated. |
| StageReceivedTime | datetime | Time when the request reached the current audit stage. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Event generation time. |
| Type | string | The name of the table |
| User | dynamic | Authenticated user metadata of the requesting client, including optional fields such as UID and groups. |
| UserAgent | string | The user agent string presented by the originating client. |
| Verb | string | The Kubernetes verb associated with the request. For non-resource requests, this is the lower-cased HTTP method. |
