---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AegDataPlaneRequests
---


| Column | Type | Description |
|---|---|---|
| Authentication | string | The type of secret used for authentication when issuing requests. Key – request uses the SAS key, SASToken – request uses a SAS token generated from SAS key, AADAccessToken – Azure Active Directory issued JSON Web Token (JWT) token, Unknown – None of the above authentication types. OPTIONS requests will have Unknown authentication type. |
| _BilledSize | real | The record size in bytes |
| ClientIpAddress | string | The IP address of the client issuing the request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NetworkAccess | string | The type of network used by the client issuing the request. Allowed values are: PublicAccess - when connecting via public IP, PrivateAccess - when connecting via private link |
| OperationName | string | The name of the operation. |
| OperationResult | string | Thw result of the operation. Possible values are: Success, Unauthorized, Forbidden, RequestEntityTooLarge, BadRequest, InternalServerError |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was generated. |
| TlsVersion | string | The transport layer security (TLS) version used by the client connection. Possible values are: 1.0, 1.1 and 1.2 |
| TotalOperations | string | The total number of request with above values issued within the minute. These traces aren't emitted for each publish request. An aggregate for each unique combination of above values is emitted every minute |
| Type | string | The name of the table |
