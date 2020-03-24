---
title: Azure Monitor Logs reference - OfficeActivity
description: Reference for OfficeActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
---

# OfficeActivity

 Audit logs for Office 365 tenants collected by Azure Sentinel. Currently only Exchange and SharePoint logs are supported.

## Categories

- Security
## Solutions

- Office 365 Analytics (Preview)
- SecurityInsights




## Columns

|Column|Type|Description|
|---|---|---|
|OfficeId|string||
|RecordType|string|Type of operation performed.|
|TimeGenerated|datetime|Date and time the record was created.|
|Operation|string|Name of the user or admin activity.|
|OrganizationId|string|The GUID for your organization's Office 365 tenant. This value will always be the same for your organization regardless of the Office 365 service in which it occurs.|
|UserType|string|The type of user that performed the operation. Possible values are Admin Application DcAdmin Regular Reserved ServicePrincipal System.|
|UserKey|string|An alternative ID for the user identified in the UserId property. For example this property is populated with the passport unique ID (PUID) for events performed by users in SharePoint OneDrive for Business and Exchange. This property may also specify the same value as the UserID property for events occurring in other services and events performed by system accounts.|
|OfficeWorkload|string|Office 365 service that the record refers to. Possible values are AzureActiveDirectory Exchange SharePoint.|
|ResultStatus|string|Indicates whether the action specified in the Operation property was successful or not. Possible values are Succeeded PartiallySucceeded or Failed. For Exchange admin activity the value is either True or False.|
|OfficeObjectId|string||
|UserId|string|The UPN (User Principal Name) of the user who performed the action that resulted in the record being logged; for example my_name@my_domain_name. Note that records for activity performed by system accounts (such as SHAREPOINT\system or NTAUTHORITY\SYSTEM) are also included.|
|ClientIP|string|IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format.|
|Site_|string|GUID of the site where the file or folder accessed by the user is located.|
|ItemType|string|Type of object that was accessed or modified. See the ItemType table for details on the types of objects.|
|EventSource|string|Identifies whether an event occurred in SharePoint. Possible values are SharePoint or ObjectModel.|
|Source_Name|string|Entity that triggered the audited operation. Possible values are SharePoint or ObjectModel.|
|UserAgent|string|Information about the user's client or browser.|
|MachineDomainInfo|string|Information about device sync operations. This information is reported only if it's present in the request.|
|MachineId|string|Information about device sync operations. This information is reported only if it's present in the request.|
|Site_Url|string|URL of the site where the file or folder accessed by the user is located.|
|SourceRelativeUrl|string|URL of the folder that contains the file accessed by the user. The combination of the values for the SiteURL SourceRelativeURL and SourceFileName parameters is the same as the value for the ObjectID property which is the full path name for the file accessed by the user.|
|SourceFileName|string|Name of the file or folder accessed by the user.|
|SourceFileExtension|string|File extension of the file that was accessed by the user. This property is blank if the object that was accessed is a folder.|
|DestinationRelativeUrl|string|URL of the destination folder where a file is copied or moved. The combination of the values for SiteURL DestinationRelativeURL and DestinationFileName parameters is the same as the value for the ObjectID property which is the full path name for the file that was copied. This property is displayed only for FileCopied and FileMoved events.|
|DestinationFileName|string|Name of the file that is copied or moved. This property is displayed only for FileCopied and FileMoved events.|
|DestinationFileExtension|string|File extension of a file that is copied or moved. This property is displayed only for FileCopied and FileMoved events.|
|UserSharedWith|string|The user that a resource was shared with.|
|SharingType|string|Type of sharing permissions that were assigned to the user that the resource was shared with. User is identified by the UserSharedWith parameter.|
|CustomEvent|string|Optional string for custom events.|
|Event_Data|string|Optional payload for custom events.|
|ModifiedProperties|string|Name of the property that was modified (for example the Site Admin group) the new value of the modified property (for example the user who was added as a site admin) and the previous value of the modified object. The property is included for admin events such as adding a user as a member of a site or a site collection admin group.|
|ModifiedObjectResolvedName|string|User friendly name of the object that was modified by the cmdlet. This is logged only if the cmdlet modifies the object.|
|Parameters|string|Name and value for all parameters that were used with the cmdlet that is identified in the Operations property.|
|ExternalAccess|string|Specifies whether the cmdlet was run by a user in your organization by Microsoft datacenter personnel or a datacenter service account or by a delegated administrator. The value False indicates that the cmdlet was run by someone in your organization. The value True indicates that the cmdlet was run by datacenter personnel a datacenter service account or a delegated administrator.|
|OriginatingServer|string|Name of the server the cmdlet was executed from.|
|OrganizationName|string|Name of the tenant.|
|Logon_Type|string|Type of user who accessed the mailbox and performed the operation that was logged.|
|InternalLogonType|int|Reserved for internal use.|
|MailboxGuid|string|Exchange GUID of the mailbox that was accessed.|
|MailboxOwnerUPN|string|Email address of the person who owns the mailbox that was accessed.|
|MailboxOwnerSid|string|SID of the mailbox owner.|
|MailboxOwnerMasterAccountSid|string|Mailbox owner account's master account SID.|
|LogonUserSid|string|SID of the user who performed the operation.|
|LogonUserDisplayName|string|User-friendly name of the user who performed the operation.|
|ClientInfoString|string|Information about the email client that was used to perform the operation such as a browser version Outlook version and mobile device information.|
|Client_IPAddress|string|IP address of the device that was used when the operation was logged. The IP address is displayed in either an IPv4 or IPv6 address format.|
|ClientMachineName|string|Machine name that hosts the Outlook client.|
|ClientProcessName|string|Email client that was used to access the mailbox.|
|ClientVersion|string|Version of the email client.|
|Folder|string|Folder where a group of items is located.|
|CrossMailboxOperations|bool|Indicates if the operation involved more than one mailbox.|
|DestMailboxId|string|GUID of the target mailbox. Set only if the CrossMailboxOperations parameter is True.|
|DestMailboxOwnerUPN|string|UPN of the owner of the target mailbox. Set only if the CrossMailboxOperations parameter is True.|
|DestMailboxOwnerSid|string|SID of the target mailbox. Set only if the CrossMailboxOperations parameter is True.|
|DestMailboxOwnerMasterAccountSid|string|SID for the master account SID of the target mailbox owner. Set only if the CrossMailboxOperations parameter is True.|
|DestFolder|string|Destination folder for operations such as Move.|
|Folders|string|Information about the source folders involved in an operation. For example specifies if folders are selected and then deleted.|
|AffectedItems|string|Information about each item in the group.|
|Item|string|Item the operation was performed was performed on.|
|SendAsUserSmtp|string|SMTP address of the user who is being impersonated.|
|SendAsUserMailboxGuid|string|Exchange GUID of the mailbox that was accessed to send email as.|
|SendOnBehalfOfUserSmtp|string|SMTP address of the user on whose behalf the email is sent.|
|SendonBehalfOfUserMailboxGuid|string|Exchange GUID of the mailbox that was accessed to send mail on behalf of.|
|AzureActiveDirectory_EventType|string|Type of Azure AD event.|
|ExtendedProperties|string|Extended properties of the Azure AD event.|
|Application|string|Application that triggers the account login event such as Office 15.|
|Client|string|Details about the client device device OS and device browser that was used for the of the account login event.|
|LoginStatus|int|This property is from OrgIdLogon.LoginStatus. The mapping of various interesting logon failures could be done by alerting algorithms.|
|UserDomain|string|Tenant Identity Information (TII).|
|Actor|string|User or service principal that performed the action.|
|ActorContextId|string|GUID of the organization that the actor belongs to.|
|ActorIpAddress|string|Actor's IP address in IPV4 or IPV6 address format.|
|InterSystemsId|string|GUID that track the actions across components within the Office 365 service.|
|IntraSystemId|string|GUID that's generated by Azure Active Directory to track the action.|
|SupportTicketId|string|Customer support ticket ID for the action in act-on-behalf-of situations.|
|AADTarget|string|User that the action was performed on. The action is identified by the Operation property.|
|TargetContextId|string|GUID of the organization that the targeted user belongs to.|
|DataCenterSecurityEventType|int||
|Start_Time|datetime|Start time of the cmdlet execution.|
|EffectiveOrganization|string|Name of the tenant that the elevation/cmdlet was targeted at.|
|ElevationTime|datetime|Start time of the elevation.|
|ElevationApprover|string|Name of a Microsoft manager.|
|ElevationApprovedTime|datetime|Timestamp for when the elevation was approved.|
|ElevationRequestId|string|Unique identifier for the elevation request.|
|ElevationRole|string|Role the elevation was requested for.|
|ElevationDuration|int|Duration for which the elevation was active.|
|GenericInfo|string||
|OfficeTenantId|string||
|SourceSystem|string|Value is OfficeActivityManager for all records in this table.|
|Type|string||
