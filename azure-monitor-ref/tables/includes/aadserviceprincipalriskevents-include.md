---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: AADServicePrincipalRiskEvents
---


| Column | Type | Description |
|---|---|---|
| Activity | string | Indicates the activity type the detected risk is linked to. |
| ActivityDateTime | datetime | Date and time when the risky activity occurred in UTC. |
| AdditionalInfo | dynamic | Additional information associated with the risk detection in JSON format. |
| AppId | string | The unique identifier for the associated application. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | Correlation ID of the sign-in activity associated with the risk detection. Nullable. |
| DetectedDateTime | datetime | Date and time when the risk was detected in UTC. |
| DetectionTimingType | string | Timing of the detected risk , whether real-time or offline. |
| Id | string | Unique identifier of the risk detection. Inherited from entity. |
| IpAddress | string | Provides the IP address of the client from where the risk occurred. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| KeyIds | dynamic | The unique identifier (GUID) for the key credential associated with the risk detection. |
| LastUpdatedDateTime | datetime | Date and time when the risk detection was last updated in UTC. |
| Location | dynamic | Location of the sign-in. |
| OperationName | string | Name of the operation. |
| RequestId | string | Request identifier of the sign-in activity associated with the risk detection. Nullable. |
| RiskDetail | string | Details of the detected risk. Note: Details for this property are only available for Azure AD Premium P2 customers. |
| RiskEventType | string | The type of risk event detected. |
| RiskLevel | string | Level of the detected risk. Note: details for this property are only available for Azure AD Premium P2 customers. |
| RiskState | string | The state of a detected risky service principal or sign-in activity. |
| ServicePrincipalDisplayName | string | The display name for the service principal. |
| ServicePrincipalId | string | The unique identifier for the service principal. |
| Source | string | Source of the risk detection. For example, identityProtection. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time of the event in UTC. |
| TokenIssuerType | string | Indicates the type of token issuer for the detected sign-in risk. |
| Type | string | The name of the table |
