---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/18/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: SigninLogs
---


| Column | Type | Description |
|---|---|---|
| AADTenantId | string |   |
| AlternateSignInName | string | The identification that the user provided to sign in. It may be the userPrincipalName but it's also populated when a user signs in using other identifiers. |
| AppDisplayName | string | The application name displayed in the Azure Portal. |
| AppId | string | The application identifier in Azure Active Directory. |
| AppliedConditionalAccessPolicies | string |   |
| AppliedEventListeners | dynamic | Detailed information about the listeners, such as Azure Logic Apps and Azure Functions, that were triggered by the corresponding events in the sign-in event. |
| AuthenticationContextClassReferences | string | Contains a collection of values that represent the conditional access authentication contexts applied to the sign-in. |
| AuthenticationDetails | string | The result of the authentication attempt and additional details on the authentication method. |
| AuthenticationMethodsUsed | string | The authentication methods used. Possible values: SMS, Authenticator App, App Verification code, Password, FIDO, PTA, or PHS. |
| AuthenticationProcessingDetails | string | Additional authentication processing details, such as the agent name in case of PTA/PHS or Server/farm name in case of federated authentication. |
| AuthenticationProtocol | string | Lists the protocol type or grant type used in the authentication. The possible values are: none, oAuth2, ropc, wsFederation, saml20, deviceCode. For authentications that use protocols other than the possible values listed, the protocol type is listed as none. |
| AuthenticationRequirement | string | This holds the highest level of authentication needed through all the sign-in steps, for sign-in to succeed. |
| AuthenticationRequirementPolicies | string | Sources of authentication requirement, such as conditional access, per-user MFA, identity protection, and security defaults. |
| AutonomousSystemNumber | string | The Autonomous System Number (ASN) of the network used by the actor. |
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| ClientAppUsed | string | The legacy client used for sign-in activity. For example: Browser, Exchange ActiveSync, Modern clients, IMAP, MAPI, SMTP, or POP. |
| ConditionalAccessPolicies | dynamic | A list of conditional access policies that are triggered by the corresponding sign-in activity. |
| ConditionalAccessStatus | string | The status of the conditional access policy triggered. Possible values: success, failure, or notApplied. |
| CorrelationId | string | The identifier that's sent from the client when sign-in is initiated. This is used for troubleshooting the corresponding sign-in activity when calling for support. |
| CreatedDateTime | datetime | The date and time the sign-in was initiated. The Timestamp type is always in UTC time. For example, midnight UTC on Jan 1, 2014 is 2014-01-01T00:00:00Z. |
| CrossTenantAccessType | string | Describes the type of cross-tenant access used by the actor to access the resource. |
| DeviceDetail | dynamic | The device information from where the sign-in occurred. Includes information such as deviceId, OS, and browser. |
| DurationMs | long |   |
| FlaggedForReview | bool | During a failed sign in, a user may click a button in the Azure portal to mark the failed event for tenant admins. If a user clicked the button to flag the failed sign in, this value is true. |
| HomeTenantId | string | The tenant identifier of the user initiating the sign in. Not applicable in Managed Identity or service principal sign ins. |
| Id | string | The identifier representing the sign-in activity. |
| Identity | string | The display name of the actor identified in the signin. |
| IPAddress | string | The IP address of the client from where the sign-in occurred. |
| IPAddressFromResourceProvider | string | The IP address a user used to reach a resource provider, used to determine Conditional Access compliance for some policies. For example, when a user interacts with Exchange Online, the IP address Exchange receives from the user may be recorded here. This value is often null. |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsInteractive | bool | Indicates whether a user sign in is interactive. In interactive sign in, the user provides an authentication factor to Azure AD. These factors include passwords, responses to MFA challenges, biometric factors, or QR codes that a user provides to Azure AD or an associated app. In non-interactive sign in, the user doesn't provide an authentication factor. Instead, the client app uses a token or code to authenticate or access a resource on behalf of a user. Non-interactive sign ins are commonly used for a client to sign in on a user's behalf in a process transparent to the user. |
| IsRisky | bool |   |
| Level | string |   |
| Location | string | The 2 letter country code from where the sign-in occurred. Depending on IP address provided, this value may not always resolve to a city or region level of detail. |
| LocationDetails | dynamic | Provides the city, state, country/region and latitude and longitude from where the sign-in happened. |
| MfaDetail | dynamic | This property is deprecated. |
| NetworkLocationDetails | string | The network location details including the type of network used and its names. |
| OperationName | string |   |
| OperationVersion | string |   |
| OriginalRequestId | string | The request identifier of the first request in the authentication sequence. |
| ProcessingTimeInMilliseconds | string |   |
| Resource | string |   |
| ResourceDisplayName | string | The name of the resource that the user signed in to. |
| ResourceGroup | string |   |
| ResourceId | string | The identifier of the resource that the user signed in to. |
| ResourceIdentity | string | The resource that the user signed in to. |
| ResourceProvider | string |   |
| ResourceServicePrincipalId | string | The identifier of the service principal representing the target resource in the sign-in event. |
| ResourceTenantId | string | The tenant identifier of the resource referenced in the sign in. |
| ResultDescription | string | Provides the error message or the reason for failure for the corresponding sign-in activity. |
| ResultSignature | string |   |
| ResultType | string | Provides the 5-6 digit error code that's generated during a sign-in event. 0 indicates success; other values are failures. You can find more information using the Azure AD Error Codes documentation or https://login.microsoftonline.com/error. |
| RiskDetail | string | The reason behind a specific state of a risky user, sign-in, or a risk event. Possible values: none, adminGeneratedTemporaryPassword, userPerformedSecuredPasswordChange, userPerformedSecuredPasswordReset, adminConfirmedSigninSafe, aiConfirmedSigninSafe, userPassedMFADrivenByRiskBasedPolicy, adminDismissedAllRiskForUser, or adminConfirmedSigninCompromised. The value none means that no action has been performed on the user or sign-in so far. Note: Details for this property are only available for Azure AD Premium P2 customers. All other customers are returned hidden. |
| RiskEventTypes | string | This property is deprecated. |
| RiskEventTypes_V2 | string | The list of risk event types associated with the sign-in. Possible values: unlikelyTravel, anonymizedIPAddress, maliciousIPAddress, unfamiliarFeatures, malwareInfectedIPAddress, suspiciousIPAddress, leakedCredentials, investigationsThreatIntelligence, or generic. |
| RiskLevel | string |   |
| RiskLevelAggregated | string | The aggregated risk level. Possible values: none, low, medium, high, or hidden. The value hidden means the user or sign-in was not enabled for Azure AD Identity Protection. Note: Details for this property are only available for Azure AD Premium P2 customers. All other customers are returned hidden. |
| RiskLevelDuringSignIn | string | The risk level during sign-in. Possible values: none, low, medium, high, or hidden. The value hidden means the user or sign-in was not enabled for Azure AD Identity Protection. Note: Details for this property are only available for Azure AD Premium P2 customers. All other customers are returned hidden. |
| RiskState | string | The risk state of a risky user, sign-in, or a risk event. Possible values: none, confirmedSafe, remediated, dismissed, atRisk, or confirmedCompromised. |
| ServicePrincipalId | string | The application identifier used for sign-in. This field is populated when you are signing in using an application. |
| ServicePrincipalName | string | The application name used for sign-in. This field is populated when you are signing in using an application. |
| SessionLifetimePolicies | string | Any conditional access session management policies that were applied during the sign-in event. |
| SignInIdentifier | string | The identification that the user provided to sign in. It may be the userPrincipalName but it's also populated when a user signs in using other identifiers. |
| SignInIdentifierType | string | The type of sign in identifier. Possible values are: userPrincipalName, phoneNumber, proxyAddress, qrCode, onPremisesUserPrincipalName. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| Status | dynamic | The sign-in status. Includes the error code and description of the error (in case of a sign-in failure). |
| TimeGenerated | datetime |   |
| TokenIssuerName | string | The name of the identity provider. For example, sts.microsoft.com. |
| TokenIssuerType | string | The type of identity provider. The possible values are: AzureAD, or ADFederationServices, AzureADBackupAuth, ADFederationServicesMFAAdapter, NPSExtension. |
| Type | string | The name of the table |
| UniqueTokenIdentifier | string | A unique base64 encoded request identifier used to track tokens issued by Azure AD as they are redeemed at resource providers. |
| UserAgent | string | The user agent information related to sign-in. |
| UserDisplayName | string | The display name of the user. |
| UserId | string | The identifier of the user. |
| UserPrincipalName | string | The UPN of the user. |
| UserType | string | Identifies whether the user is a member or guest in the tenant. Possible values are: member and guest. |
