---
title: Azure Monitor Logs reference - IntuneDeviceComplianceOrg
description: Reference for IntuneDeviceComplianceOrg table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/9/2020
---

# IntuneDeviceComplianceOrg

 Intune device compliance specialist report.

## Categories

- IT & Management Tools
## Solutions

- LogManagement
## Resource types

- Intune Specialist Reports.




## Columns

|Column|Type|Description|
|---|---|---|
|AADTenantId|string|The AAD Tenant ID|
|BatchId|string|The unique ID for the exported report|
|ComplianceState|string|The compliance state of the device|
|DeviceHealthThreatLevel|string|The device health threat level|
|DeviceId|string|The ID of the device|
|DeviceName|string|The name of the device|
|DeviceType|string|The type of the device|
|IMEI|string|The international mobile equipment identifier of the device|
|InGracePeriodUntil|string|The device grace period end time|
|IntuneAccountId|string|The Intune Account ID|
|LastContact|string|The date and time of last contact|
|ManagementAgents|string|The management agents|
|OperationName|string|The name of the operation|
|OS|string|The operating system of the device|
|OSDescription|string|The operating system of the device|
|OSVersion|string|The version of the operating system|
|OwnerType|string|The type of owner|
|Result|string|The result of the operation|
|RetireAfterDatetime|string|The date time after which the device will be retired|
|SerialNumber|string|The serial number of the device|
|SourceSystem|string|Details of source system of the object being provisioned|
|Stats|dynamic|Statistics about the export, including the number of records exported per export|
|TenantId|string||
|TimeGenerated|datetime|Date and time when the report was generated (UTC)|
|Type|string|The name of the table|
|UPN|string|The user principal name|
|UserEmail|string|The user email address|
|UserId|string|The ID of the user|
|UserName|string|The user name|
