---
title: Azure Monitor Logs reference - SigninLogs
description: Reference for SigninLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# SigninLogs

 Sign-in logs for Azure Active Directory. Includes information about the usage of managed applications and user sign-in activities.

## Categories

- Azure Resources
- Security
## Solutions

- LogManagement




## Columns

|Column|Type|Description|
|---|---|---|
|SourceSystem|string||
|TimeGenerated|datetime|Date and time the record was created.|
|ResourceId|string|ID of the resource that the user signed into.|
|OperationName|string|For sign-ins this value is always Sign-in activity.|
|OperationVersion|string|REST API version that's requested by the client.|
|Category|string|For sign-ins this value is always SignIn.|
|ResultType|string|Result of the sign-in operation. Possible values are Success and Failure.|
|ResultSignature|string|Error code if any for the sign-in operation.|
|ResultDescription|string|Error description for the sign-in operation.|
|DurationMs|long|Deprecated.|
|CorrelationId|string|Optional GUID that's passed by the client. This value can help correlate client-side operations with server-side operations and it's useful when you're tracking logs that span services.|
|Resource|string||
|ResourceGroup|string||
|ResourceProvider|string||
|Identity|string|Identity from the token that was presented when the request was made. Can be a user account system account or service principal.|
|Level|string|Type of message. For audit this is always Informational.|
|Location|string|Location of the sign-in activity.|
|AppDisplayName|string|Application name displayed in the Azure Portal.|
|AppId|string|Unique GUID representing Application Id in the Azure Active Directory.|
|ClientAppUsed|string|Legacy client used for sign-in activty. Possible values include Browser Exchange Active SyncModern clients IMAP MAPI SMTP POP.|
|ConditionalAccessPolicies|dynamic|List of conditional access policies that are triggered by the corresponding sign-in activity.|
|ConditionalAccessStatus|string|Status of the conditional access policy triggered. Possible values are success failure notApplied unknownFutureValue.|
|CreatedDateTime|datetime|Date and time the sign-in was initiated in UTC.|
|DeviceDetail|dynamic|Device information from where the sign-in occurred; includes device ID operating system and browser.|
|Id|string|Unique ID representing the sign-in activity.|
|IPAddress|string|IP address of the client where the sign-in occurred.|
|IsRisky|bool||
|LocationDetails|dynamic|Details about the network location.|
|RiskDetail|string|Reason behind a specific state of a risky user sign-in or a risk event. Possible values are none adminGeneratedTemporaryPassword userPerformedSecuredPasswordChange userPerformedSecuredPasswordReset adminConfirmedSigninSafe aiConfirmedSigninSafe userPassedMFADrivenByRiskBasedPolicy adminDismissedAllRiskForUser adminConfirmedSigninCompromised unknownFutureValue. The value none means that no action has been performed on the user or sign-in so far.|
|RiskLevelAggregated|string|Aggregated risk level. Possible values are none low medium high hidden and unknownFutureValue. The value hidden means the user or sign-in was not enabled for Azure AD Identity Protection. Details for this property are only available for Azure AD Premium P2 customers. All other customers will be returned hidden.|
|RiskState|string|Reports status of the risky user sign-in or a risk event. Possible values are none confirmedSafe remediated dismissed atRisk confirmedCompromised unknownFutureValue.|
|RiskLevelDuringSignIn|string|Risk level during sign-in. The possible values are: none low medium high hidden and unknownFutureValue. The value hidden means the user or sign-in was not enabled for Azure AD Identity Protection.|
|RiskEventTypes|string|Risk event types associated with the sign-in. Possible values are unlikelyTravel anonymizedIPAddress maliciousIPAddress unfamiliarFeatures malwareInfectedIPAddress suspiciousIPAddress leakedCredentials investigationsThreatIntelligence generic and unknownFutureValue.|
|Status|dynamic|Provides the sign-in status. Possible values include Success and Failure.|
|UserDisplayName|string|Display Name of the User.|
|UserId|string|User ID of the user.|
|UserPrincipalName|string|UPN of the user.|
|AADTenantId|string|ID of the AAD tenant.|
|ResourceDisplayName|string|Name of the resource that the user signed into.|
|OriginalRequestId|string|ID of the resource that the user signed into.|
|Type|string||
