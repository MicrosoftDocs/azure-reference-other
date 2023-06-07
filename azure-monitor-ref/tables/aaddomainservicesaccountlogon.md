---
title: Azure Monitor Logs reference - AADDomainServicesAccountLogon
description: Reference for AADDomainServicesAccountLogon table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/1/2023
---

# AADDomainServicesAccountLogon

 

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
| CertIssuerName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| CertSerialNumber | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| CertThumbprint | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| ClientUserName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| CorrelationId | string |  |
| FailureCode | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| IpAddress | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| IpPort | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| _IsBillable | string |  |
| MappedName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| MappingBy | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| OperationName | string |  |
| PackageName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| PreAuthType | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| RecordId | string | A unique identifier corresponding to this record. |
| ResourceId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string |  |
| ResultType | string |  |
| ServiceName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| SourceSystem | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TicketOptions | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TimeGenerated | datetime |  |
| Type | string | The name of the table |
