---
title: Azure Monitor Logs reference - PowerBIActivity
description: Reference for PowerBIActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# PowerBIActivity

 Contains Microsoft PowerBI audit logs. It's typically used to track PowerBI activities.

## Categories

- Security
- Audit
## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Activity | string | The name of the user or admin activity. |
| ActivityId | string | A unique identifier for the activity. |
| ActorName | string | The UPN (User Principal Name) of the user who performed the action (specified in the Operation property) that resulted in the record being logged; for example, my_name@my_domain_name. Note that records for activity performed by system accounts (such as SHAREPOINT\system or NT AUTHORITY\SYSTEM) are also included. In SharePoint, another value display in the UserId property is app@sharepoint. This indicates that the "user" who performed the activity was an application that has the necessary permissions in SharePoint to perform organization-wide actions (such as search a SharePoint site or OneDrive account) on behalf of a user, admin, or service. For more information, see the app@sharepoint user in audit records. |
| ActorUserId | string | An alternative ID for the user identified in the UserId property. For example, this property is populated with the passport unique ID (PUID) for events performed by users in SharePoint, OneDrive for Business, and Exchange. This property may also specify the same value as the UserID property for events occurring in other services and events performed by system accounts. |
| ActorUserType | string | The type of user that performed the operation. Possible types are: Admin, System, Application, Service Principal and Other. |
| DashboardId | string | The ID of the dashboard that the activity was performed on. |
| DashboardName | string | The name of the dashboard where the event occurred. |
| DataClassification | string | The data classification, if exists, for the dashboard where the event occurred. |
| DatasetName | string | The name of the dataset where the event occurred. |
| DistributionMethod | string | Indicates the distribution method of the content. |
| EventOriginalType | string | The name of the user or admin activity that performed the activity. For a description of the most common operations/activities, see "Search the audit log" in the Office 365 Protection Center. For Exchange admin activity, this property identifies the name of the cmdlet that was run. For Dlp events, this can be "DlpRuleMatch", "DlpRuleUndo" or "DlpInfo", which are described under "DLP schema" below. |
| EventOriginalUid | string | Unique identifier of an audit record. |
| EventProduct | string | The Microsoft product name (PowerBI). |
| EventResult | string | Indicates whether the action (specified in the Operation property) was successful or not. Possible values are Succeeded, PartiallySucceeded, or Failed. |
| EventVendor | string | Service vendor name. |
| IsSuccess | string | Indicates whether the action was successful or not. |
| ItemName | string | The name of the item that the activity was performed on. |
| MembershipInformation | string | Membership information about the group. |
| ObjectId | string | The full path name of the file or folder accessed by the user. For Exchange admin audit logging, the name of the object that was modified by the cmdlet. |
| OrganizationId | string | The GUID for your organization's Office 365 tenant. This value will always be the same for your organization, regardless of the Office 365 service in which it occurs. |
| OrgAppPermission | string | Permissions list for an organizational app (entire organization, specific users, or specific groups). |
| PbiWorkspaceName | string | The name of the PowerBI workspace where the event occurred. |
| RecordType | string | The type of operation indicated by the record. See the AuditLogRecordType table for details on the types of audit log records. |
| ReportName | string | The name of the report where the event occurred. |
| RequestId | string | A unique identifier for the request. |
| Scope | string | Event can be created by a hosted Office 365 service or an on-premises server. Possible values are online and onprem. Note that SharePoint is the only workload currently sending events from on-premises to Office 365. |
| SharingInformation | string | Information about the person to whom a sharing invitation is sent. |
| SourceSystem | string |  |
| SrcIpAddr | string | The IP address of the device that was used when the activity was logged. The IP address is displayed in either an IPv4 or IPv6 address format. For some services, the value displayed in this property might be the IP address for a trusted application (for example, Office on the web apps) calling into the service on behalf of a user and not the IP address of the device used by person who performed the activity. Also, for Azure Active Directory-related events, the IP address isn't logged and the value for the ClientIP property is null. |
| SwitchState | string | Information about the state of various tenant level switches. |
| TargetAppName | string | The name of the app where the event occurred. |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time in (UTC) when the user performed the activity. |
| Type | string | The name of the table |
| UserAgent | string | Information about the user's browser. This information is provided by the browser. |
| UserType | string | The type of user that performed the operation. Possible types are: Admin, System, Application, Service Principal and Other. |
| Workload | string | The Office 365 service where the activity occurred. |
| WorkspaceId | string | The ID of the PowerBI workspace. |
