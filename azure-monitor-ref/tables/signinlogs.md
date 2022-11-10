---
title: Azure Monitor Logs reference - SigninLogs
description: Reference for SigninLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# SigninLogs

 

## Categories

- Azure Resources
- Security
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AADTenantId | string |  |
| AlternateSignInName | string |  |
| AppDisplayName | string |  |
| AppId | string |  |
| AuthenticationContextClassReferences | string |  |
| AuthenticationDetails | string |  |
| AuthenticationMethodsUsed | string |  |
| AuthenticationProcessingDetails | string |  |
| AuthenticationRequirement | string |  |
| AuthenticationRequirementPolicies | string |  |
| AutonomousSystemNumber | string |  |
| Category | string |  |
| ClientAppUsed | string |  |
| ConditionalAccessPolicies | dynamic |  |
| ConditionalAccessStatus | string |  |
| CorrelationId | string |  |
| CreatedDateTime | datetime |  |
| DeviceDetail | dynamic |  |
| DurationMs | long |  |
| FlaggedForReview | bool |  |
| HomeTenantId | string |  |
| Id | string |  |
| Identity | string |  |
| IPAddress | string |  |
| IPAddressFromResourceProvider | string |  |
| IsInteractive | bool |  |
| IsRisky | bool |  |
| Level | string |  |
| Location | string |  |
| LocationDetails | dynamic |  |
| MfaDetail | dynamic |  |
| NetworkLocationDetails | string |  |
| OperationName | string |  |
| OperationVersion | string |  |
| OriginalRequestId | string |  |
| ProcessingTimeInMilliseconds | string |  |
| Resource | string |  |
| ResourceDisplayName | string |  |
| ResourceGroup | string |  |
| ResourceId | string |  |
| ResourceIdentity | string |  |
| ResourceProvider | string |  |
| ResourceServicePrincipalId | string |  |
| ResourceTenantId | string |  |
| ResultDescription | string |  |
| ResultSignature | string |  |
| ResultType | string |  |
| RiskDetail | string |  |
| RiskEventTypes | string |  |
| RiskEventTypes_V2 | string |  |
| RiskLevelAggregated | string |  |
| RiskLevelDuringSignIn | string |  |
| RiskState | string |  |
| ServicePrincipalId | string |  |
| ServicePrincipalName | string |  |
| SessionLifetimePolicies | string |  |
| SignInIdentifier | string |  |
| SignInIdentifierType | string |  |
| SourceSystem | string |  |
| Status | dynamic |  |
| TimeGenerated | datetime |  |
| TokenIssuerName | string |  |
| TokenIssuerType | string |  |
| Type | string | The name of the table |
| UniqueTokenIdentifier | string |  |
| UserAgent | string |  |
| UserDisplayName | string |  |
| UserId | string |  |
| UserPrincipalName | string |  |
| UserType | string |  |
