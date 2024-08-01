---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AADUserRiskEvents
---


| Column | Type | Description |
|---|---|---|
| Activity | string | Indicates the activity type the detected risk is linked to. Possible values are: signin, user, unknownFutureValue. |
| ActivityDateTime | datetime | Date and time when the risky activity occurred. |
| AdditionalInfo | dynamic | Additional information associated with the user risk event in JSON format. |
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | Correlation ID of the sign-in associated with the risk detection. This property is null if the risk detection is not associated with a sign-in. |
| DetectedDateTime | datetime | Date and time that the risk was detected. |
| DetectionTimingType | string | Timing of the detected risk (real-time/offline). Possible values are: notDefined, realtime, nearRealtime, offline, unknownFutureValue. |
| Id | string | Unique ID of the risk event. |
| IpAddress | string | The IP address of the client from where the risk occurred. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| LastUpdatedDateTime | datetime | Date and time when the risk detection was last updated. |
| Location | dynamic | Location of the sign-in. |
| OperationName | string | Name of the operation. |
| RequestId | string | Request ID of the sign-in associated with the risk detection. This property is null if the risk detection is not associated with a sign-in. |
| RiskDetail | string | Details of the detected risk. Possible values are: none, adminGeneratedTemporaryPassword, userPerformedSecuredPasswordChange, userPerformedSecuredPasswordReset, adminConfirmedSigninSafe, aiConfirmedSigninSafe, userPassedMFADrivenByRiskBasedPolicy, adminDismissedAllRiskForUser, adminConfirmedSigninCompromised, hidden, adminConfirmedUserCompromised, unknownFutureValue. |
| RiskEventType | string | The type of risk event detected. |
| RiskLevel | string | Level of the detected risk. Possible values are: low, medium, high, hidden, none, unknownFutureValue. |
| RiskState | string | The state of a detected risky user or sign-in. Possible values are: none, confirmedSafe, remediated, dismissed, atRisk, confirmedCompromised, unknownFutureValue. |
| Source | string | Source of the risk detection. For example, activeDirectory. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time of the event in UTC. |
| TokenIssuerType | string | Indicates the type of token issuer for the detected sign-in risk. Possible values are: AzureAD, ADFederationServices, UnknownFutureValue. |
| Type | string | The name of the table |
| UserDisplayName | string | The user principal name (UPN) of the user. |
| UserId | string | Unique ID of the user. |
| UserPrincipalName | string | The user principal name (UPN) of the user. |
