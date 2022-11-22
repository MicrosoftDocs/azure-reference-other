---
title: Azure Monitor Logs reference - OfficeActivity
description: Reference for OfficeActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/17/2022
---

# OfficeActivity

 Audit logs for Office 365 tenants collected by Azure Sentinel. Including Exchange, SharePoint and Teams logs.

## Categories

- Security
## Solutions

- AzureSentinelPrivatePreview
- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AADGroupId | string | Azure Active Directory group id |
| AADTarget | string | The user that the action (identified by the Operation property) was performed on |
| Actor | string | The user or service principal that performed the action |
| ActorContextId | string | The GUID of the organization that the actor belongs to |
| ActorIpAddress | string | The actor's IP address in IPV4 or IPV6 address format |
| AddOnGuid | string | The unique identifier of the add-on generated this event |
| AddonName | string | The name of the add-on that generated this event |
| AddOnType | string | The type of add-on that generated this event |
| AffectedItems | string | Information about each item in the group |
| AppDistributionMode | string | Application distribution mode |
| AppId | string | Application ID |
| Application | string | The application name |
| ApplicationId | string | SharePoint application ID |
| AzureActiveDirectory_EventType | string | The type of Azure AD event |
| AzureADAppId | string | Teams Application Azure AD ID |
| ChannelGuid | string | A unique identifier for the channel being audited |
| ChannelName | string | The name of the channel being audited |
| ChannelType | string | The type of channel being audited (Standard/Private) |
| ChatName | string | The name of the chat |
| ChatThreadId | string | The Id of the chat thread |
| Client | string | Details about the client device, device OS, and device browser that was used for the of the account login event |
| ClientAppId | string | Client application ID |
| ClientInfoString | string | Information about the email client that was used to perform the operation |
| ClientIP | string | The IP address of the device that was used when the activity was logged |
| Client_IPAddress | string | The IP address of the device that was used when the operation was logged |
| ClientMachineName | string | The machine name that hosts the Outlook client |
| ClientProcessName | string | The email client that was used to access the mailbox |
| ClientVersion | string | The version of the email client  |
| CommunicationType | string | The type of communications that was conducted |
| CrossMailboxOperations | bool | Indicates if the operation involved more than one mailbox |
| CustomEvent | string | Optional string for custom events |
| DataCenterSecurityEventType | int | The type of dmdlet event in lock box |
| DestFolder | string | The destination folder |
| DestinationFileExtension | string | The file extension of a file that is copied or moved |
| DestinationFileName | string | The name of the file that is copied or moved |
| DestinationRelativeUrl | string | The URL of the destination folder where a file is copied or moved |
| DestMailboxId | string | Set only if the CrossMailboxOperations parameter is True |
| DestMailboxOwnerMasterAccountSid | string | Set only if the CrossMailboxOperations parameter is True |
| DestMailboxOwnerSid | string | Set only if the CrossMailboxOperations parameter is True |
| DestMailboxOwnerUPN | string | Set only if the CrossMailboxOperations parameter is True |
| EffectiveOrganization | string | The name of the tenant that the elevation/cmdlet was targeted at |
| ElevationApprovedTime | datetime | The timestamp for when the elevation was approved |
| ElevationApprover | string | The name of a Microsoft manager |
| ElevationDuration | int | The duration for which the elevation was active (in Hours) |
| ElevationRequestId | string | A unique identifier for the elevation request |
| ElevationRole | string | The role the elevation was requested for |
| ElevationTime | datetime | The start time of the elevation |
| Event_Data | string | Optional payload for custom events |
| EventSource | string | Identifies that an event occurred in SharePoint. Possible values are SharePoint or ObjectModel |
| ExtendedProperties | string | The extended properties of the Azure AD event |
| ExternalAccess | string | Specifies whether the cmdlet was run by a user in your organization |
| ExtraProperties | dynamic | A list of extra properties |
| Folder | string | The folder where a group of items is located |
| Folders | string | Information about the source folders involved in an operation |
| GenericInfo | string | Used for comments and other generic information |
| InternalLogonType | int | Reserved for internal use |
| InterSystemsId | string | The GUID that track the actions across components within the Office 365 service |
| IntraSystemId | string | The GUID that's generated by Azure Active Directory to track the action |
| IsManagedDevice | bool | Indicates if operation was created by a device managed by the organization |
| Item | string | Represents the item upon which the operation was performed |
| ItemName | string | The string in the Subject field of the email message |
| ItemType | string | The type of object that was accessed or modified. See the ItemType table for details on the types of objects |
| LoginStatus | int | This property is from OrgIdLogon.LoginStatus directly. The mapping of various interesting logon failures could be done by alerting algorithms |
| Logon_Type | string | Indicates the type of user who accessed the mailbox and performed the operation that was logged |
| LogonUserDisplayName | string | The user-friendly name of the user who performed the operation |
| LogonUserSid | string | The SID of the user who performed the operation |
| MachineDomainInfo | string | Information about device sync operations |
| MachineId | string | Information about device sync operations |
| MailboxGuid | string | The Exchange GUID of the mailbox that was accessed |
| MailboxOwnerMasterAccountSid | string | Mailbox owner account's master account SID |
| MailboxOwnerSid | string | The SID of the mailbox owner |
| MailboxOwnerUPN | string | The email address of the person who owns the mailbox that was accessed |
| Members | dynamic | A list of users within a Team |
| MessageId | string | An identifier for a chat or channel message |
| ModifiedObjectResolvedName | string | This is the user friendly name of the object that was modified by the cmdlet |
| ModifiedProperties | string | The property is included for admin events, such as adding a user as a member of a site or a site collection admin group |
| Name | string | Only present for settings events. Name of the setting that changed |
| NewValue | string | Only present for settings events. New value of the setting |
| OfficeId | string | Unique identifier of an audit record |
| OfficeObjectId | string | For SharePoint and OneDrive for Business activity |
| OfficeTenantId | string | The office tenant id |
| OfficeWorkload | string | The Office 365 service where the activity occurred |
| OldValue | string | Only present for settings events. Old value of the setting |
| Operation | string | The name of the operation that the user is performing |
| OperationProperties | dynamic | Additional operation properties |
| OperationScope | string | The scope the operation was performed on |
| OrganizationId | string | The GUID for your organization's Office 365 tenant. This value will always be the same for your organization |
| OrganizationName | string | The name of the tenant |
| OriginatingServer | string | The name of the server from which the cmdlet was executed |
| Parameters | string | The name and value for all parameters that were used with the cmdlet that is identified in the Operations property |
| RecordType | string | The type of operation indicated by the record. See the AuditLogRecordType table for details on the types of audit log records |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultReasonType | string | Reason for the result reported in ResultType |
| ResultStatus | string | Indicates whether the action (specified in the Operation property) was successful or not |
| SendAsUserMailboxGuid | string | The Exchange GUID of the mailbox that was accessed to send email as |
| SendAsUserSmtp | string | SMTP address of the user who is being impersonated |
| SendonBehalfOfUserMailboxGuid | string | The Exchange GUID of the mailbox that was accessed to send mail on behalf of |
| SendOnBehalfOfUserSmtp | string | SMTP address of the user on whose behalf the email is sent |
| SharingType | string | The type of sharing permissions that were assigned to the user that the resource was shared with. This user is identified by the UserSharedWith parameter |
| Site_ | string | The GUID of the site where the file or folder accessed by the user is located |
| Site_Url | string | The URL of the site where the file or folder accessed by the user is located |
| SourceFileExtension | string | The file extension of the file that was accessed by the user |
| SourceFileName | string | The name of the file or folder accessed by the user |
| Source_Name | string | The entity that triggered the audited operation. Possible values are SharePoint or ObjectModel |
| SourceRecordId | string | Unique identifier of an audit record |
| SourceRelativeUrl | string | The URL of the folder that contains the file accessed by the user |
| SourceSystem | string | The source system name |
| SRPolicyId | string | Policy ID |
| SRPolicyName | string | Policy name |
| SRRuleMatchDetails | dynamic | Rule details |
| Start_Time | datetime | The date and time at which the cmdlet was executed |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SupportTicketId | string | The customer support ticket ID for the action in 'act-on-behalf-of' situations |
| TabType | string | The type of tab that generated this event |
| TargetContextId | string | The GUID of the organization that the targeted user belongs to |
| TargetUserId | string | Target user id |
| TargetUserOrGroupName | string | Stores the UPN or name of the target user or group that a resource was shared with |
| TargetUserOrGroupType | string | Identifies whether the target user or group is a Member, Guest, Group, or Partner |
| TeamGuid | string | A unique identifier for the team being audited |
| TeamName | string | The name of the team being audited |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time in Coordinated Universal Time (UTC) when the user performed the activity |
| Type | string | The name of the table |
| UserAgent | string | The user agent |
| UserDomain | string | The domain of the user |
| UserId | string | The UPN (User Principal Name) of the user who performed the action (specified in the Operation property) that resulted in the record being logged |
| UserKey | string | An alternative ID for the user identified in the UserId property |
| UserSharedWith | string | The user that a resource was shared with |
| UserType | string | The type of user that performed the operation. See the UserType table for  details on the types of users |
