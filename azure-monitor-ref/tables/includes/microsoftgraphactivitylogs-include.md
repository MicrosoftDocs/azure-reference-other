---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: MicrosoftGraphActivityLogs
---


| Column | Type | Description |
|---|---|---|
| AadTenantId | string | The Azure AD tenant ID. |
| ApiVersion | string | The API version of the event. |
| AppId | string | The identifier for the application. |
| ATContent | string | Reserved for future use. |
| _BilledSize | real | The record size in bytes |
| ClientAuthMethod | int | Indicates how the client was authenticated. For a public client, the value is 0. If client ID and client secret are used, the value is 1. If a client certificate was used for authentication, the value is 2. |
| ClientRequestId | string | Optional. The client request identifier when sent. If no client request identifier is sent, the value will be equal to the operation identifier. |
| DurationMs | int | The duration of the request in milliseconds. |
| IdentityProvider | string | The identity provider that authenticated the subject of the token. |
| IPAddress | string | The IP address of the client from where the request occurred. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Location | string | The name of the region that served the request. |
| OperationId | string | The identifier for the batch. For non-batched requests, this will be unique per request. For batched requests, this will be the same for all requests in the batch. |
| RequestId | string | The identifier representing the request. |
| RequestMethod | string | The HTTP method of the event. |
| RequestUri | string | The URI of the request. |
| ResponseSizeBytes | int | The size of the response in Bytes. |
| ResponseStatusCode | int | The HTTP response status code for the event. |
| Roles | string | The roles in token claims. |
| Scopes | string | The scopes in token claims. |
| ServicePrincipalId | string | The identifier of the servicePrincipal making the request. |
| SignInActivityId | string | The identifier representing the sign-in activitys. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time the request was received. |
| TokenIssuedAt | datetime | The timestamp the token was issued at. |
| Type | string | The name of the table |
| UserAgent | string | The user agent information related to request. |
| UserId | string | The identifier of the user making the request. |
| Wids | string | Denotes the tenant-wide roles assigned to this user. |
