---
title: Azure Monitor Logs reference - Update
description: Reference for Update table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/26/2023
---

# Update

 Details for update schedule run. Includes information such as which updates where available and which were installed.

## Categories

- IT & Management Tools
- Security
## Solutions

- Security and Audit
- SecurityCenter
- SecurityCenterFree
- Update Management
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets
- Automation account




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ApprovalSource | string |  |
| Approved | bool |  |
| _BilledSize | real |  |
| BulletinID | string |  |
| BulletinUrl | string |  |
| Classification | string |  |
| Computer | string |  |
| ComputerEnvironment | string |  |
| CVENumbers | string |  |
| InstallTimeAvailable | bool |  |
| InstallTimeDeviationRangeSeconds | real |  |
| InstallTimePredictionSeconds | real |  |
| _IsBillable | string |  |
| KBID | string |  |
| ManagementGroupName | string |  |
| MSRCBulletinID | string |  |
| MSRCSeverity | string |  |
| Optional | bool |  |
| OSFullName | string |  |
| OSName | string |  |
| OSType | string |  |
| OSVersion | string |  |
| PackageRepository | string |  |
| PackageSeverity | string |  |
| Product | string |  |
| ProductArch | string |  |
| ProductVersion | string |  |
| PublishedDate | datetime |  |
| RebootBehavior | string |  |
| Resource | string |  |
| ResourceGroup | string |  |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProvider | string |  |
| ResourceType | string |  |
| RevisionNumber | string |  |
| SourceComputerId | string |  |
| SourceSystem | string |  |
| SubscriptionId | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| Title | string |  |
| Type | string | The name of the table |
| UpdateID | string |  |
| UpdateState | string |  |
| VMUUID | string |  |
