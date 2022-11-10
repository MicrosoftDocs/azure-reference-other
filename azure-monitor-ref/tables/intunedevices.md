---
title: Azure Monitor Logs reference - IntuneDevices
description: Reference for IntuneDevices table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/10/2022
---

# IntuneDevices

 Intune devices specialist report.

## Categories

- IT & Management Tools
## Solutions

- LogManagement




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AADTenantId | string | The AAD Tenant ID |
| AndroidPatchLevel | string | The Android patch level of the device |
| BatchId | string | The unique ID for the exported report |
| CategoryName | string | The category name of the device |
| CompliantState | string | The compliant state of the device |
| CreatedDate | string | The date and time of the device entry was created |
| DeviceId | string | The ID of the device |
| DeviceName | string | The name of the device |
| DeviceRegistrationState | string | The registration state of the device |
| DeviceState | string | The state of the device |
| EasID | string | The Emergency Alert System Identification of the device |
| EncryptionStatusString | string | String describing whether the device is encrypted |
| GraphDeviceIsManaged | bool | Boolean describing whether the graph device is managed |
| IMEI | string | The international mobile equipment identifier of the device |
| InGracePeriodUntil | string | The device grace period end time |
| IntuneAccountId | string | The Intune Account ID |
| JailBroken | string | String describing whether the device is jail broken |
| JoinType | string | The device join type |
| LastContact | string | The date and time of last contact |
| ManagedBy | string | The authority that the device is managed by |
| ManagedDeviceName | string | The managed device name |
| Manufacturer | string | The manufacturer of the device |
| MEID | string | The mobile equipment identifier of the device |
| Model | string | The model of the device |
| OperationName | string | The name of the operation |
| OS | string | The operating system of the device |
| OSVersion | string | The version of the operating system |
| Ownership | string | The ownership of the device |
| PhoneNumber | string | The phone number |
| PrimaryUser | string | The ID of the primary user |
| ReferenceId | string | The AAD Device ID |
| Result | string | The result of the operation |
| SerialNumber | string | The serial number of the device |
| SkuFamily | string | The stock-keeping unit family of the device |
| SourceSystem | string | Details of source system of the object being provisioned |
| Stats | dynamic | Statistics about the export, including the number of records exported per export |
| StorageFree | long | The free storage size of the device |
| StorageTotal | long | The total storage size of the device |
| SubscriberCarrierNetwork | string | The subscriber carrier network |
| SupervisedStatusString | string | String describing whether the device is supervised |
| TenantId | string |  |
| TimeGenerated | datetime | Date and time when the report was generated (UTC) |
| Type | string | The name of the table |
| UPN | string | The user principal name |
| UserEmail | string | The user email address |
| UserName | string | The user name |
| WifiMacAddress | string | The WiFi MAC address of the device |
