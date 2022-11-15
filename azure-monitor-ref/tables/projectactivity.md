---
title: Azure Monitor Logs reference - ProjectActivity
description: Reference for ProjectActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# ProjectActivity

 Contains your Microsoft Project audit logs in order to track your Project activities.

## Categories

- Security
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActorName | string | The UPN (User Principal Name) of the user who performed the action (specified in the Operation property) that resulted in the record being logged; for example, my_name@my_domain_name. Note that records for activity performed by system accounts (such as SHAREPOINT\system or NT AUTHORITY\SYSTEM) are also included. In SharePoint, another value display in the UserId property is app@sharepoint. This indicates that the "user" who performed the activity was an application that has the necessary permissions in SharePoint to perform organization-wide actions (such as search a SharePoint site or OneDrive account) on behalf of a user, admin, or service. For more information, see the app@sharepoint user in audit records. |
| ActorUserId | string | An alternative ID for the user identified in the UserId property. For example, this property is populated with the passport unique ID (PUID) for events performed by users in SharePoint, OneDrive for Business, and Exchange. This property may also specify the same value as the UserID property for events occurring in other services and events performed by system accounts. |
| ActorUserType | string | The type of user that performed the operation. Possible types are: Admin, System, Application, Service Principal and Other. |
| EventOriginalType | string | The name of the user or admin activity that performed the activity. For a description of the most common operations/activities, see "Search the audit log" in the Office 365 Protection Center. For Exchange admin activity, this property identifies the name of the cmdlet that was run. For Dlp events, this can be "DlpRuleMatch", "DlpRuleUndo" or "DlpInfo", which are described under "DLP schema" below. |
| EventOriginalUid | string | Unique identifier of an audit record. |
| EventProduct | string | The Microsoft service name. |
| EventResult | string | Indicates whether the action (specified in the Operation property) was successful or not. Possible values are Succeeded, PartiallySucceeded, or Failed. |
| EventVendor | string | The vendor service name. |
| ObjectId | string | For SharePoint and OneDrive for business activity, the full path name of the file or folder accessed by the user. For Exchange admin audit logging, the name of the object that was modified by the cmdlet. |
| OnBehalfOfResId | string | The resource ID the action was taken on behalf of. |
| OrganizationId | string | The GUID for your organization's Office 365 tenant. This value will always be the same for your organization, regardless of the Office 365 service in which it occurs. |
| ProjectAction | string | The project action that was taken. |
| ProjectEntity | string | The project entity the audit was for. |
| RecordType | string | The type of operation indicated by the record. See the AuditLogRecordType table for details on the types of audit log records. |
| Scope | string | Event can be created by a hosted Office 365 service or an on-premises server. Possible values are online and onprem. Note that SharePoint is the only workload currently sending events from on-premises to Office 365. |
| SourceSystem | string |  |
| SrcIpAddr | string | The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format. For some services, the value displayed in this property might be the IP address for a trusted application (for example, Office on the web apps) calling into the service on behalf of a user and not the IP address of the device used by person who performed the activity. Also, for Azure Active Directory-related events, the IP address isn't logged and the value for the ClientIP property is null. |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time in UTC when the user performed the activity. |
| Type | string | The name of the table |
| UserType | string | The type of user that performed the operation. |
| Workload | string | The Office 365 service where the activity occurred. |
