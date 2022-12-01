---
title: Azure Monitor Logs reference - Dynamics365Activity
description: Reference for Dynamics365Activity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
---

# Dynamics365Activity

 Audit logs for Dynamics 365 tenants collected by Azure Sentinel.

## Solutions

- Microsoft Sentinel




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ClientIP | string | The IP address of the device that was used when the activity was logged |
| CorrelationId | string | A unique value used to associate related rows |
| CrmOrganizationUniqueName | string | Unique name of the organization |
| EntityId | string | Unique identifier of the entity |
| EntityName | string | Name of the entity in the organization |
| Fields | dynamic | JSON of Key Value pair reflecting the values that were created or updated |
| InstanceUrl | string | URL to the instance |
| ItemType | string | The type of object that was accessed or modified. See the ItemType table for details on the types of objects |
| ItemUrl | string | URL to the record emitting the log |
| Message | string | Name of the message called in the Dynamics365 SDK |
| OfficeWorkload | string | The Office 365 service where the activity occurred |
| Operation | string | The name of the operation that the user is performing |
| OrganizationId | string | The GUID for your organization's Office 365 tenant. This value will always be the same for your organization |
| OriginalObjectId | string | The ObjectId for SharePoint and OneDrive about business activity |
| Query | string | The query filter parameters used while executing the FetchXML |
| QueryResults | dynamic | One or multiple unique records returned by the Retrieve and Retrieve Multiple SDK message call |
| RecordType | string | The type of operation indicated by the record. See the AuditLogRecordType table in Office 365 management activity api schema documentation for details on the types of audit log records |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultStatus | string | Indicates whether the action (specified in the Operation property) was successful or not |
| ServiceName | string | Name of the Service generating the log |
| SourceRecordId | string | Unique identifier of an audit record |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SystemUserId | string | Unique identifier of the user GUID in the organization |
| TenantId | string |  |
| TimeGenerated | datetime | The date and time in Coordinated Universal Time (UTC) when the user performed the activity |
| Type | string | The name of the table |
| UserAgent | string | The user agent |
| UserId | string | The UPN (User Principal Name) of the user who performed the action (specified in the Operation property) that resulted in the record being logged |
| UserKey | string | An alternative ID for the user identified in the UserId property |
| UserType | string | The type of user that performed the operation. See the UserType table in Office 365 management activity api schema documentation for details on the types of users |
