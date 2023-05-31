---
title: Azure Monitor Logs reference - AADDomainServicesPrivilegeUse
description: Reference for AADDomainServicesPrivilegeUse table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 5/26/2023
---

# AADDomainServicesPrivilegeUse

 

## Categories

- Azure Resources
- Security
## Solutions

- LogManagement
## Resource types

- Azure AD Domain Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| _BilledSize | real |  |
| Category | string |  |
| CorrelationId | string |  |
| _IsBillable | string |  |
| NewState | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| OperationName | string |  |
| ProcessId | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| ProcessName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| RecordId | string | A unique identifier corresponding to this record. |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceManager | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| ResultDescription | string |  |
| ResultType | string |  |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime |  |
| TransactionId | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| Type | string | The name of the table |
