---
title: Azure Monitor Logs reference - Dynamics365Activity
description: Reference for Dynamics365Activity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# Dynamics365Activity

 Audit logs for Dynamics 365 tenants collected by Azure Sentinel.

## Solutions

- Azure Sentinel




## Columns

|Column|Type|Description|
|---|---|---|
|Application|string|The application name|
|ClientIP|string|The IP address of the device that was used when the activity was logged|
|EntityName|string|Name of the entity in the organization|
|InstanceUrl|string|URL to the instance|
|ItemType|string|The type of object that was accessed or modified. See the ItemType table for details on the types of objects|
|Message|string|Name of the message called in the SDK|
|OfficeWorkload|string|The Office 365 service where the activity occurred|
|Operation|string|The date and time in Coordinated Universal Time (UTC) when the user performed the activity|
|OrganizationId|string|The GUID for your organization's Office 365 tenant. This value will always be the same for your organization|
|OriginalObjectId|string|The ObjectId for SharePoint and OneDrive about business activity|
|RecordType|string|The type of operation indicated by the record. See the AuditLogRecordType table for details on the types of audit log records|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResultStatus|string|Indicates whether the action (specified in the Operation property) was successful or not|
|ServiceName|string|Name of the Service generating the log|
|SourceRecordId|string|Unique identifier of an audit record|
|SourceSystem|string||
|TenantId|string||
|TimeGenerated|datetime|The date and time in Coordinated Universal Time (UTC) when the user performed the activity|
|Type|string|The name of the table|
|UserAgent|string|The user agent|
|UserDomain|string|The domain of the user|
|UserId|string|The UPN (User Principal Name) of the user who performed the action (specified in the Operation property) that resulted in the record being logged|
|UserKey|string|An alternative ID for the user identified in the UserId property|
|UserType|string|The type of user that performed the operation. See the UserType table for  details on the types of users|
