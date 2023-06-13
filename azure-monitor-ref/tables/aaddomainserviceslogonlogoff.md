---
title: Azure Monitor Logs reference - AADDomainServicesLogonLogoff
description: Reference for AADDomainServicesLogonLogoff table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/13/2023
---

# AADDomainServicesLogonLogoff

 

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
| AuthenticationPackageName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| _BilledSize | real |  |
| Category | string |  |
| CorrelationId | string |  |
| ElevatedToken | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| FailureReason | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| ImpersonationLevel | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| _IsBillable | string |  |
| KeyLength | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| LmPackageName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| LogonGuid | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| LogonProcessName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| LogonType | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| OperationName | string |  |
| RecordId | string | A unique identifier corresponding to this record. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| RestrictedAdminMode | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| ResultDescription | string |  |
| ResultType | string |  |
| SidList | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubStatus | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetDomainName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetInfo | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetLinkedLogonId | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetLogonGuid | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetLogonId | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetOutboundDomainName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetOutboundUserName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetServerName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetUserName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TargetUserSid | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TdoSid | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| TimeGenerated | datetime |  |
| TransmittedServices | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| Type | string | The name of the table |
| VirtualAccount | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
| WorkstationName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName.  Please see the Windows Server description of this event for the meaning of this field. |
