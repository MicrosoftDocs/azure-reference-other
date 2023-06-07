---
title: Azure Monitor Logs reference - AADDomainServicesDNSAuditsGeneral
description: Reference for AADDomainServicesDNSAuditsGeneral table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/1/2023
---

# AADDomainServicesDNSAuditsGeneral

 DNS server audit events enable change tracking on the DNS server. An audit event is logged each time server, zone, or resource record settings are changed. This includes operational events such as zone transfers, and DNSSEC zone signing and unsigning.  This table captures audit events that are not from dynamic updates.

## Solutions

- LogManagement
## Resource types

- Azure AD Domain Services




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Action | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ActiveKey | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Base64Data | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| _BilledSize | real |  |
| BufferSize | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ChildZone | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ClientSubnetList | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ClientSubnetRecord | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Condition | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Criteria | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| CryptoAlgorithm | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| CurrentRolloverStatus | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| CurrentState | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DenialOfExistence | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Digest | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DigestType | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DistributeTrustAnchor | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DnsKeyRecordSetTtl | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DnsKeySignatureValidityPeriod | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DSRecordGenerationAlgorithm | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DSRecordSetTtl | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| DSSignatureValidityPeriod | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| EnableRfc5011KeyRollover | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ErrorsPerSecond | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| EventGuid | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| EventString | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| FilePath | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Forwarders | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| FriendlyName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| InitialRolloverOffset | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| IPv4PrefixLength | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| IPv6PrefixLength | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| _IsBillable | string |  |
| IsEnabled | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| IsKeyMasterServer | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyId | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyLength | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyMasterServer | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyOrZone | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyProtocol | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyStorageProvider | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyTag | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KeyType | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| KskOrZsk | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| LastRolloverTime | datetime | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| LeakRate | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ListenAddresses | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Lookup | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| MasterServer | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Mode | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Name | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NameServer | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NewFriendlyName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NewPropertyValues | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NewScope | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NewValue | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NextKey | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NextRolloverAction | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NextRolloverTime | datetime | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NodeName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NSec3HashAlgorithm | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NSec3Iterations | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NSec3OptOut | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NSec3RandomSaltLength | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| NSec3UserSalt | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| OldFriendlyName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| OldPropertyValues | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| OldScope | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| operationName | string | Identifies the type of event emitted. |
| operationVersion | string | Version string.  Reserved. |
| ParentHasSecureDelegation | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Policy | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ProcessingOrder | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| PropagationTime | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| PropertyKey | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| QName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| QType | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| RData | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| RecordId | string | Identifier for the underlying Windows event |
| RecursionScope | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ReplicationScope | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResponsePerSecond | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| resultDescription | string | Summary description of the event. |
| RolloverPeriod | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| RolloverType | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| RRLExceptionlist | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ScavengeServers | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Scope | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Scopes | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ScopeWeight | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ScopeWeightNew | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ScopeWeightOld | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| SecureDelegationPollingPeriod | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| SeizedOrTransfered | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ServerName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Setting | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| SignatureInceptionOffset | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| SourceSystem | string |  |
| StandbyKey | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| StoreKeysInAD | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| SubTreeAging | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| TCRate | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| TenantId | string |  |
| TimeGenerated | datetime | The timestamp (UTC) of when the event was generated. |
| TotalResponsesInWindow | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Ttl | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Type | string | The name of the table |
| VirtualizationID | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| WindowSize | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| WithNewKeys | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| WithWithout | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| Zone | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ZoneFile | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ZoneName | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ZoneScope | string | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
| ZoneSignatureValidityPeriod | int | The context of this field is dependent on the Windows Event being emitted, represented in the OperationName. Please see the Windows Server description of this event for the meaning of this field. |
