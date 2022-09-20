---
title: Azure Monitor Logs reference - SecurityEvent
description: Reference for SecurityEvent table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/8/2022
---

# SecurityEvent

 Security events collected from windows machines by Azure Security Center or Azure Sentinel.

## Categories

- Security
## Solutions

- Security and Audit
- Microsoft Sentinel
## Resource types

- Virtual machines
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccessMask | string |  |
| Account | string | Domain and username of the account that made the actin |
| AccountDomain | string |  |
| AccountExpires | string |  |
| AccountName | string |  |
| AccountSessionIdentifier | string |  |
| AccountType | string |  |
| Activity | string | ID and Description of the event. |
| AdditionalInfo | string |  |
| AdditionalInfo2 | string |  |
| AllowedToDelegateTo | string |  |
| Attributes | string |  |
| AuditPolicyChanges | string |  |
| AuditsDiscarded | int |  |
| AuthenticationLevel | int |  |
| AuthenticationPackageName | string |  |
| AuthenticationProvider | string |  |
| AuthenticationServer | string |  |
| AuthenticationService | int |  |
| AuthenticationType | string |  |
| AzureDeploymentID | string | Azure deployment ID of the cloud service the log belongs to. Only populated when events are collected using Azure Diagnostics agent and collected from Azure storage. |
| CACertificateHash | string |  |
| CalledStationID | string |  |
| CallerProcessId | string |  |
| CallerProcessName | string |  |
| CallingStationID | string |  |
| CAPublicKeyHash | string |  |
| CategoryId | string |  |
| CertificateDatabaseHash | string |  |
| Channel | string |  |
| ClassId | string |  |
| ClassName | string |  |
| ClientAddress | string |  |
| ClientIPAddress | string |  |
| ClientName | string |  |
| CommandLine | string |  |
| CompatibleIds | string |  |
| Computer | string | Name of the computer that the event was collected from. |
| DCDNSName | string |  |
| DeviceDescription | string |  |
| DeviceId | string |  |
| DisplayName | string |  |
| Disposition | string |  |
| DomainBehaviorVersion | string |  |
| DomainName | string |  |
| DomainPolicyChanged | string |  |
| DomainSid | string |  |
| EAPType | string |  |
| ElevatedToken | string |  |
| ErrorCode | int |  |
| EventData | string | 	All event data in raw format. |
| EventID | int | Number of the event. |
| EventSourceName | string |  |
| ExtendedQuarantineState | string |  |
| FailureReason | string |  |
| FileHash | string |  |
| FilePath | string |  |
| FilePathNoUser | string |  |
| Filter | string |  |
| ForceLogoff | string |  |
| Fqbn | string |  |
| FullyQualifiedSubjectMachineName | string |  |
| FullyQualifiedSubjectUserName | string |  |
| GroupMembership | string |  |
| HandleId | string |  |
| HardwareIds | string |  |
| HomeDirectory | string |  |
| HomePath | string |  |
| InterfaceUuid | string |  |
| IpAddress | string |  |
| IpPort | string |  |
| KeyLength | int |  |
| Level | string |  |
| LmPackageName | string |  |
| LocationInformation | string |  |
| LockoutDuration | string |  |
| LockoutObservationWindow | string |  |
| LockoutThreshold | string |  |
| LoggingResult | string |  |
| LogonGuid | string |  |
| LogonHours | string |  |
| LogonID | string |  |
| LogonProcessName | string |  |
| LogonType | int |  |
| LogonTypeName | string |  |
| MachineAccountQuota | string |  |
| MachineInventory | string |  |
| MachineLogon | string |  |
| ManagementGroupName | string | Name of the management group for System Center Operations Manager agents. For other agents this value is AOI-<workspace ID> |
| MandatoryLabel | string |  |
| MaxPasswordAge | string |  |
| MemberName | string |  |
| MemberSid | string |  |
| MinPasswordAge | string |  |
| MinPasswordLength | string |  |
| MixedDomainMode | string |  |
| NASIdentifier | string |  |
| NASIPv4Address | string |  |
| NASIPv6Address | string |  |
| NASPort | string |  |
| NASPortType | string |  |
| NetworkPolicyName | string |  |
| NewDate | string |  |
| NewMaxUsers | string |  |
| NewProcessId | string |  |
| NewProcessName | string |  |
| NewRemark | string |  |
| NewShareFlags | string |  |
| NewTime | string |  |
| NewUacValue | string |  |
| NewValue | string |  |
| NewValueType | string |  |
| ObjectName | string |  |
| ObjectServer | string |  |
| ObjectType | string |  |
| ObjectValueName | string |  |
| OemInformation | string |  |
| OldMaxUsers | string |  |
| OldRemark | string |  |
| OldShareFlags | string |  |
| OldUacValue | string |  |
| OldValue | string |  |
| OldValueType | string |  |
| OperationType | string |  |
| PackageName | string |  |
| ParentProcessName | string |  |
| PasswordHistoryLength | string |  |
| PasswordLastSet | string |  |
| PasswordProperties | string |  |
| PreviousDate | string |  |
| PreviousTime | string |  |
| PrimaryGroupId | string |  |
| PrivateKeyUsageCount | string |  |
| PrivilegeList | string |  |
| Process | string |  |
| ProcessId | string |  |
| ProcessName | string |  |
| ProfilePath | string |  |
| Properties | string |  |
| ProtocolSequence | string |  |
| ProxyPolicyName | string |  |
| QuarantineHelpURL | string |  |
| QuarantineSessionID | string |  |
| QuarantineSessionIdentifier | string |  |
| QuarantineState | string |  |
| QuarantineSystemHealthResult | string |  |
| RelativeTargetName | string |  |
| RemoteIpAddress | string |  |
| RemotePort | string |  |
| Requester | string |  |
| RequestId | string |  |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| RestrictedAdminMode | string |  |
| RowsDeleted | string |  |
| SamAccountName | string |  |
| ScriptPath | string |  |
| SecurityDescriptor | string |  |
| ServiceAccount | string |  |
| ServiceFileName | string |  |
| ServiceName | string |  |
| ServiceStartType | int |  |
| ServiceType | string |  |
| SessionName | string |  |
| ShareLocalPath | string |  |
| ShareName | string |  |
| SidHistory | string |  |
| SourceComputerId | string |  |
| SourceSystem | string | Type of agent the event was collected from. Possible values are OpsManager Linux and AzureStorage. |
| Status | string |  |
| StorageAccount | string |  |
| SubcategoryGuid | string |  |
| SubcategoryId | string |  |
| Subject | string |  |
| SubjectAccount | string |  |
| SubjectDomainName | string |  |
| SubjectKeyIdentifier | string |  |
| SubjectLogonId | string |  |
| SubjectMachineName | string |  |
| SubjectMachineSID | string |  |
| SubjectUserName | string |  |
| SubjectUserSid | string |  |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubStatus | string |  |
| TableId | string |  |
| TargetAccount | string |  |
| TargetDomainName | string |  |
| TargetInfo | string |  |
| TargetLinkedLogonId | string |  |
| TargetLogonGuid | string |  |
| TargetLogonId | string |  |
| TargetOutboundDomainName | string |  |
| TargetOutboundUserName | string |  |
| TargetServerName | string |  |
| TargetSid | string |  |
| TargetUser | string |  |
| TargetUserName | string |  |
| TargetUserSid | string |  |
| Task | int |  |
| TemplateContent | string |  |
| TemplateDSObjectFQDN | string |  |
| TemplateInternalName | string |  |
| TemplateOID | string |  |
| TemplateSchemaVersion | string |  |
| TemplateVersion | string |  |
| TimeGenerated | datetime | Date and time the record was created. |
| TokenElevationType | string |  |
| TransmittedServices | string |  |
| Type | string | The name of the table |
| UserAccountControl | string |  |
| UserParameters | string |  |
| UserPrincipalName | string |  |
| UserWorkstations | string |  |
| VendorIds | string |  |
| VirtualAccount | string |  |
| Workstation | string | Name of the computer where the action happened. |
| WorkstationName | string |  |
