---
title: Azure Monitor Logs reference - IdentityInfo
description: Reference for IdentityInfo table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/24/2022
---

# IdentityInfo

 This table is populated by Azure Sentinel UEBA with all your users identities information. It can be used to correlate user information and insights with analytics or hunting queries.

## Solutions

- Microsoft Sentinel UEBA




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountCloudSID | string | The Azure AD security identifier of the account |
| AccountCreationTime | datetime | The date the user account was created (UTC) |
| AccountDisplayName | string | The user account display name |
| AccountDomain | string | Domain name of the user account |
| AccountName | string | User name of the account |
| AccountObjectId | string | The Azure Active Directory object ID for the account |
| AccountSID | string | The on premises security identifier of the account |
| AccountTenantId | string | The Azure Active Directory Tenant ID of the account |
| AccountUPN | string | User principal name of the account |
| AdditionalMailAddresses | dynamic | Additional email addresses of the user |
| Applications | string | All known applications this user account accessed |
| AssignedRoles | dynamic | AAD roles the user account is assigned to |
| BlastRadius | string | The potential impact of the user account in the org (low/medium/high) |
| ChangeSource | string | The source of the latest change of the entity |
| City | string | The city of the user account as defined in AAD |
| Country | string | The country of the user account as defined in AAD |
| DeletedDateTime | datetime | The date and time the user was deleted |
| Department | string | The user account department as defined in AAD |
| EmployeeId | string | The employee identifier assigned to the user by the organization |
| EntityRiskScore | dynamic | The risk score of the entity as part of the UEBA scoring process |
| ExtensionProperty | dynamic | ExtensionProperty fields from Azure AD |
| GivenName | string | The user account given name |
| GroupMembership | dynamic | Azure AD Groups the user account is a member |
| InvestigationPriority | int | The Investigation Priority score of the account |
| InvestigationPriorityPercentile | int | The account score compared to the organization  |
| IsAccountEnabled | bool | Indication if the account is enabled in AAD or not |
| IsMFARegistered | bool | Indication if MFA is registered for this user account or not |
| JobTitle | string | The user account job title as defined in AAD |
| LastSeenDate | datetime | Date of the last activity observed in this account |
| MailAddress | string | The user account primary email address |
| Manager | string | The user accounts manager alias |
| OnPremisesDistinguishedName | string | Active Directory distinguished name (DN). A DN is a sequence of relative distinguished names (RDN) connected by commas. |
| OnPremisesExtensionAttributes | string | OnPremisesExtensionAttributes field from Azure AD |
| Phone | string | The phone number of the user account as defined in AAD |
| RelatedAccounts | dynamic | Various accounts that correlate to a certain user |
| RiskLevel | string | The AAD risk level (Low/Medium/High) of the user account |
| RiskLevelDetails | string | Details regarding the AAD risk level |
| RiskState | string | Indication if the account is at risk now or if the risk was remediated |
| ServicePrincipals | dynamic | Azure AD service principals that are owned by the user |
| SourceSystem | string | The system where the user is managed |
| State | string | The geographical state of the user account as defined in AAD |
| StreetAddress | string | The office street address of the user account as defined in AAD |
| Surname | string | The user account surname |
| Tags | string | Relevant information on the user account which is important for investigation: Sensitive\ VIP\  Administrator |
| TenantId | string |  |
| TimeGenerated | datetime | Time when the event was generated (UTC) |
| Type | string | The name of the table |
| UACFlags | string | User Access control flags from AD & AAD |
| UserAccountControl | dynamic | Security attributes of the user account in the AD domain |
| UserState | string | The current state in AAD of the account (Active/Disabled/Dormant/Lockout) |
| UserStateChangedOn | datetime | Date of the last time the account state was changed (UTC) |
| UserType | string | The user type as appears in Azure AD |
