---
title: Azure Monitor Logs reference - IntuneDeviceComplianceOrg
description: Reference for IntuneDeviceComplianceOrg table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# IntuneDeviceComplianceOrg

 Intune device compliance specialist report.

## Categories

- IT & Management Tools
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| ComplianceState | string | The compliance state of the device. |
| DeviceHealthThreatLevel | string | The device health threat level. |
| DeviceId | string | The Id of the device. |
| DeviceName | string | The name of the device. |
| DeviceType | string | The type of the device. |
| IMEI | string | The international mobile equipment identifier of the device. |
| InGracePeriodUntil | string | The device grace period end time. |
| _IsBillable | string |  |
| LastContact | string | The date and time of last contact. |
| ManagementAgents | string | The management agents. |
| OS | string | The operating system of the device. |
| OSDescription | string | The operating system of the device. |
| OSVersion | string | The version of the operating system. |
| OwnerType | string | The type of owner. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| Result | string | The result of the operation. |
| RetireAfterDatetime | string | The retire after date time. |
| SerialNumber | string | The serial number of the device |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Date and time when the report was generated. |
| Type | string | The name of the table |
| UPN | string | The user principal name. |
| UserEmail | string | The user email address. |
| UserId | string | The Id of the user. |
| UserName | string | The user name. |
