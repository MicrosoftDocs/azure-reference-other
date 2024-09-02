---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: orens
author: osalzberg
ms.custom: EGNFailedHttpDataPlaneOperations
---


| Column | Type | Description |
|---|---|---|
| AuthenticationType | string | Type of authentication used by the client. SharedAccessKey - request uses the SAS key, SharedAccessSignature - request uses a SAS token generated from SAS key, EntraIdAccessToken - Microsoft Entra issued JSON Web Token (JWT) token, Unknown - None of the above authentication types. |
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | The IP address of the client issuing the request. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| NetworkAccess | string | The type of network used by the client issuing the request. Allowed values are: PublicAccess - when connecting via public IP, PrivateAccess - when connecting via private link |
| ObjectId | string | The Microsoft Entra ObjectId of the caller issuing the request. |
| OperationName | string | The name of the operation. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultSignature | string | The result of the operation. Possible values are: ServiceError, ClientError, QuotaExceeded, AuthnError, AuthzError, ConnectionLost |
| ResultType | string | The type of the result. Possible values are: Failed. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (UTC) when the log was generated. |
| TLSVersion | string | The transport layer security (TLS) version used by the client connection. Possible values are: 1.2 and 1.3 |
| TotalOperations | string | The total number of request with above values issued within the minute. These traces aren't emitted for each request. An aggregate for each unique combination of above values is emitted every minute |
| Type | string | The name of the table |
