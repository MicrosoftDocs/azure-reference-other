---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AADNonInteractiveUserSignInLogs
---


| Column | Type | Description |
|---|---|---|
| AlternateSignInName | string | Provides the on-premises UPN of the user sign-ing into Azure AD.e.g. Phone number sign-in. |
| AppDisplayName | string | App name displayed in the Azure portal. |
| AppId | string | Unique GUID representing the app ID in the Azure Active Directory. |
| AppliedEventListeners | dynamic | Detailed information about the applied event listeners or listeners that are triggered by the corresponding events in an authentication activity. It's called appliedEventListeners in ALP and MSGraph, but use Authentication Events to match name on UX. |
| AuthenticationContextClassReferences | string | The authentication contexts of the sign-in. |
| AuthenticationDetails | string | A record of each step of authentication undertaken in the sign-in. |
| AuthenticationMethodsUsed | string | List of authentication methods used. |
| AuthenticationProcessingDetails | string | Provides the details associated with authentication processor. |
| AuthenticationProtocol | string | Lists the protocol type or grant type used in the authentication. The possible values are: none, oAuth2, ropc, wsFederation, saml20, deviceCode, unknownFutureValue. For authentications that use protocols other than the possible values listed, the protocol type is listed as none. |
| AuthenticationRequirement | string | Type of authentication required for the sign-in.  If set to multiFactorAuthentication, an MFA step was required.  If set to singleFactorAuthentication, no MFA was required. |
| AuthenticationRequirementPolicies | string | Set of CA policies that apply to this sign-in, each as CA: policy name, and/or MFA: Per-user. |
| AutonomousSystemNumber | string | Autonomous System Number for the network. |
| _BilledSize | real | The record size in bytes |
| Category | string | Category of the sign-in event. |
| ClientAppUsed | string | Details outlining app auth used (Legacy vs non Legacy) Eg: Modern Browser, Native App, Exchange Activty Sync and Older Clients. |
| ConditionalAccessPolicies | string | Details of the conditional access policies being applied for the sign-in. |
| ConditionalAccessStatus | string | Status of all the conditionalAccess policies related to the sign-in. |
| CorrelationId | string | ID to provide sign-in trail. |
| CreatedDateTime | datetime | Datetime of the sign-in activity. |
| CrossTenantAccessType | string | Describes the type of cross-tenant access used by the actor to access the resource. Possible values are: none, b2bCollaboration, b2bDirectConnect, microsoftSupport, serviceProvider, unknownFutureValue. If the sign in did not cross tenant boundaries, the value is none. |
| DeviceDetail | string | Details of the device used for the sign-in. |
| DurationMs | long | The duration of the operation in milliseconds. |
| HomeTenantId | string | The home tenant ID for cross-tenant scenarios. |
| Id | string | Unique ID representing the sign-in activity. |
| Identity | string | The identity from the token that was presented when you made the request. It can be a user account, system account, or service principal. |
| IPAddress | string | IP address of the client used to sign in. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsInteractive | bool | Indicates if a sign-in is interactive or not. |
| IsRisky | bool | Indicates if a sign-in is considered risky or not. |
| Level | string | The severity level of the event. |
| Location | string | The region of the resource emitting the event. |
| LocationDetails | string | Details of the sign-in location. |
| MfaDetail | string | Details of the Multi-factor authentication. |
| NetworkLocationDetails | string | Provides the details associated with authentication processor. |
| OperationName | string | For sign-ins, this value is always Sign-in activity. |
| OperationVersion | string | The REST API version that's requested by the client. |
| OriginalRequestId | string | The request id of the first request in the authentication sequence. |
| ProcessingTimeInMs | string | Request processing time in milliseconds in AD STS. |
| ResourceDisplayName | string | Name of the resource that the user signed into. |
| ResourceGroup | string | Resource group for the logs. |
| ResourceIdentity | string | ID of the resource that the user signed into. |
| ResourceServicePrincipalId | string | Service Principal Id of the resource. |
| ResourceTenantId | string | The resource tenant ID for cross-tenant scenarios. |
| ResultDescription | string | Provides the error description for the sign-in operation. |
| ResultSignature | string | Contains the error code, if any, for the sign-in operation. |
| ResultType | string | The result of the sign-in operation can be Success or Failure. |
| RiskDetail | string | Risky user state details. |
| RiskEventTypes | string | The list of risk event types associated with the sign-in. |
| RiskEventTypes_V2 | string | The list of risk event types associated with the sign-in. These are strings. |
| RiskLevelAggregated | string | Aggregated risk level. |
| RiskLevelDuringSignIn | string | Risk level during sign-in. |
| RiskState | string | Risky user state. |
| ServicePrincipalId | string | ID of the service principal who initiated the sign-in. |
| SessionLifetimePolicies | string | Policies and settings that applied to the sign-in that enforced or revoked a session lifetime. |
| SignInEventTypes | string | The types that are associated with the sign-in.  Examples include "interactive", "refreshToken", "managedIdentity", "continuousAccessEvaluation" and many more. |
| SignInIdentifierType | string | The type of sign in identifier. Possible values are: userPrincipalName, phoneNumber, proxyAddress, qrCode, onPremisesUserPrincipalName, unknownFutureValue. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | string | Details of the sign-in status. |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | The date and time of the event in UTC. |
| TokenIssuerName | string | Name of the identity provider (e.g. sts.microsoft.com ). |
| TokenIssuerType | string | Type of identityProvider (Azure AD, AD Federation Services). |
| Type | string | The name of the table |
| UniqueTokenIdentifier | string | Unique token identifier for the request. |
| UserAgent | string | User Agent for the sign-in. |
| UserDisplayName | string | Display name of the user that initiated the sign-in. |
| UserId | string | ID of the user that initiated the sign-in. |
| UserPrincipalName | string | User principal name of the user that initiated the sign-in. |
| UserType | string | Identifies whether the user is a member or guest in the tenant. Possible values are: member, guest, unknownFutureValue. |
