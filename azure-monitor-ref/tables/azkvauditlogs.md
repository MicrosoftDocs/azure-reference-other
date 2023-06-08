---
title: Azure Monitor Logs reference - AZKVAuditLogs
description: Reference for AZKVAuditLogs table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 6/8/2023
---

# AZKVAuditLogs

 Audit logs can be used to log and monitor events happening on your vaults including vault modifications, access.

## Categories

- Azure Resources
- Audit
## Solutions

- LogManagement
## Resource types

- Key Vaults




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AddressAuthorizationType | string | Address Type (Public IP, Subnet, private connection) |
| Algorithm | string | Algorithm used to generate the key. |
| AppliedAssignmentId | string | AssignmentId that eiher granted or denied access as part of access check. |
| _BilledSize | real |  |
| CallerIpAddress | string | IP address of the client that made the request |
| ClientInfo | string | User agent information. |
| CorrelationId | string | An optional GUID that the client can pass to correlate client-side logs with service-side (Key Vault) logs. |
| DurationMs | int | Time it took to service the REST API request, in milliseconds. This does not include the network latency, so the time you measure on the client side might not match this time. |
| EnabledForDeployment | bool | Specifies if the vault is enabled for deployment. |
| EnabledForDiskEncryption | bool | Specifes if Disk Encryption is enabled. |
| EnabledForTemplateDeployment | bool | Specifies whether template deployment is enabled. |
| EnablePurgeProtection | bool | Specifies if Purge Protection is enabled. |
| EnableRbacAuthorization | bool | Specifies if RBAC authorization is enabled. |
| EnableSoftDelete | bool | Specified is the vault is enabled for Soft Delete. |
| HsmPoolResourceId | string | Resource ID of the HSM pool. |
| HttpStatusCode | int | HTTP Status code of the request. |
| Id | string | ResourceIdentifier (Key ID or Secret ID). |
| Identity | dynamic | Identity from the token that was presented in the REST API request. This is usually a user, a service principal, or the combination user+appId, as in the case of a request that results from an Azure PowerShell cmdlet. |
| IsAccessPolicyMatch | bool | True if the tenant matches vault tenant, and if the policy explicitly gives permission to the principal attempting the access. |
| IsAddressAuthorized | bool | Specifies whether request came from an authorized entity. |
| _IsBillable | string |  |
| IsRbacAuthorized | bool | Specifies whether an access was granted or not as part of an access check. |
| Nsp | dynamic | Network Security Perimeter Properties including Access Control List, Nsp ID's associated with profiles. |
| OperationName | string | Name of the operation |
| Properties | dynamic | Information that varies based on the operation (operationName). In most cases, this field contains client information (the user agent string passed by the client), the exact REST API request URI, and the HTTP status code. In addition, when an object is returned as a result of a request (for example, KeyCreate or VaultGet), it also contains the key URI (as id), vault URI, or secret URI. |
| RequestUri | string | URI of the request. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional description about the result, when available. |
| ResultSignature | string | HTTP status of the Request/Response |
| ResultType | string | Result of the REST API request. |
| SoftDeleteRetentionInDays | int | Specifies Soft Delete Retention in Days. |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| SubnetId | string | Id of subnet if request comes from a known subnet. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when operation occured. |
| Tlsversion | string | Network Crypto protocol. |
| TrustedService | string | Specifies whether the principal access the service is a trusted Service. If this field is null, principal is not a trusted service. |
| Type | string | The name of the table |
