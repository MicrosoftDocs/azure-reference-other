---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AADRiskyUsers
---


| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| CorrelationId | string | The ID for correlated log analytics events. Can be used to identify correlated events between multiple tables. |
| Id | string | Unique ID of the user at risk. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsDeleted | bool | Indicates whether the user is deleted. |
| IsProcessing | bool | Indicates whether a user's risky state is being processed by the backend. |
| OperationName | string | Name of the operation. |
| RiskDetail | string | Details of the detected risk. Possible values are: none, adminGeneratedTemporaryPassword, userPerformedSecuredPasswordChange, userPerformedSecuredPasswordReset, adminConfirmedSigninSafe, aiConfirmedSigninSafe, userPassedMFADrivenByRiskBasedPolicy, adminDismissedAllRiskForUser, adminConfirmedSigninCompromised, hidden, adminConfirmedUserCompromised, unknownFutureValue. |
| RiskLastUpdatedDateTime | datetime | The date and time that the risky user was last updated. |
| RiskLevel | string | Level of the detected risky user. Possible values are: low, medium, high, hidden, none, unknownFutureValue. |
| RiskState | string | State of the user's risk. Possible values are: none, confirmedSafe, remediated, dismissed, atRisk, confirmedCompromised, unknownFutureValue. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time of the event in UTC. |
| Type | string | The name of the table |
| UserDisplayName | string | Risky user display name. |
| UserPrincipalName | string | Risky user principal name. |
