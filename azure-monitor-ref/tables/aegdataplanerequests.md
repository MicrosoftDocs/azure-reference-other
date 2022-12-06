---
title: Azure Monitor Logs reference - AegDataPlaneRequests
description: Reference for AegDataPlaneRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# AegDataPlaneRequests

 Logs for Event Grid data plane requests (publish and options) against a topic/domain/partnernamespace. It can be used for auditing purposes. Logs are aggregated over a minute and displays the total number of requests with specific request properties.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Event Grid Topics
- Event Grid Domains
- Event Grid Partner Namespaces




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Authentication | string | The type of secret used for authentication when issuing requests. Key – request uses the SAS key, SASToken – request uses a SAS token generated from SAS key, AADAccessToken – Azure Active Directory issued JSON Web Token (JWT) token, Unknown – None of the above authentication types. OPTIONS requests will have Unknown authentication type. |
| ClientIpAddress | string | The IP address of the client issuing the request. |
| NetworkAccess | string | The type of network used by the client issuing the request. Allowed values are: PublicAccess - when connecting via public IP, PrivateAccess - when connecting via private link |
| OperationName | string | The name of the operation. |
| OperationResult | string | Thw result of the operation. Possible values are: Success, Unauthorized, Forbidden, RequestEntityTooLarge, BadRequest, InternalServerError |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (UTC) when the log was generated. |
| TlsVersion | string | The transport layer security (TLS) version used by the client connection. Possible values are: 1.0, 1.1 and 1.2 |
| TotalOperations | string | The total number of request with above values issued within the minute. These traces aren't emitted for each publish request. An aggregate for each unique combination of above values is emitted every minute |
| Type | string | The name of the table |
