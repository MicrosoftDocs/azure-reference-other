---
ms.service: azure-monitor
ms.topic: include
ms.date: 07/30/2024
ms.author: orens
author: osalzberg
ms.custom: AZKVAuditLogs
---


| Column | Type | Description |
|---|---|---|
| AddressAuthorizationType | string | Address type (Public IP, subnet, private connection) |
| Algorithm | string | Algorithm used to generate the key |
| AppliedAssignmentId | string | AssignmentId that eiher granted or denied access as part of access check |
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | IP address of the client that made the request |
| CertificateIssuerProperties | dynamic | Information about certificate issuer properties including provider, id |
| CertificatePolicyProperties | dynamic | Information about certificate policy properties including keyproperties, secretproperties, issuerproperties |
| CertificateProperties | dynamic | Information about certificate audit properties including atttributes, subject, hashing algorithm |
| CertificateRequestProperties | dynamic | Boolean value indicating if certificate request operation was cancelled |
| ClientInfo | string | User agent information |
| CorrelationId | string | An optional GUID that the client can pass to correlate client-side logs with service-side (Key Vault) logs. |
| DurationMs | int | Time it took to service the REST API request, in milliseconds. This does not include the network latency, so the time you measure on the client side might not match this time |
| EnabledForDeployment | bool | Specifies if the vault is enabled for deployment |
| EnabledForDiskEncryption | bool | Specifes if disk encryption is enabled |
| EnabledForTemplateDeployment | bool | Specifies whether template deployment is enabled |
| EnablePurgeProtection | bool | Specifies if purge protection is enabled |
| EnableRbacAuthorization | bool | Specifies if RBAC authorization is enabled |
| EnableSoftDelete | bool | Specified is the vault is enabled for soft delete |
| HsmPoolResourceId | string | Resource ID of the HSM pool |
| HttpStatusCode | int | HTTP status code of the request |
| Id | string | Resourceidentifier (Key ID or secret ID) |
| Identity | dynamic | Identity from the token that was presented in the REST API request. This is usually a user, a service principal, or the combination user+appId, as in the case of a request that results from an Azure PowerShell cmdlet. |
| IsAccessPolicyMatch | bool | True if the tenant matches vault tenant, and if the policy explicitly gives permission to the principal attempting the access. |
| IsAddressAuthorized | bool | Specifies whether request came from an authorized entity |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| IsRbacAuthorized | bool | Specifies whether an access was granted or not as part of an access check |
| KeyProperties | dynamic | Information about key properties including type, size, curve |
| NetworkAcls | dynamic | Information about network acls that govern access to the vault |
| Nsp | dynamic | Network security perimeter properties including access control list, nsp id's associated with profiles. |
| OperationName | string | Name of the operation |
| OperationVersion | string | REST api version requested by the client. |
| Properties | dynamic | Information that varies based on the operation (Operationname). In most cases, this field contains client information (the user agent string passed by the client), the exact REST API request URI, and the HTTP status code. In addition, when an object is returned as a result of a request (for example, KeyCreate or VaultGet), it also contains the key URI (as id), vault URI, or secret URI. |
| RequestUri | string | URI of the request |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResultDescription | string | Additional description about the result, when available. |
| ResultSignature | string | HTTP status of the request/response |
| ResultType | string | Result of the REST API request. |
| SecretProperties | dynamic | Information about secret properties including type, atttributes |
| Sku | dynamic | Information about vault including family, name and capacity |
| SoftDeleteRetentionInDays | int | Specifies soft delete retention in days |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| StorageAccountProperties | dynamic | Information about storage account properties including activekeyname, resourceid |
| StorageSasDefinitionProperties | dynamic | Information about storage sas definition properties including sastype, validityperiod |
| SubnetId | string | Id of subnet if request comes from a known subnet |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp (in UTC) when operation occured. |
| Tlsversion | string | Network crypto protocol |
| TrustedService | string | Specifies whether the principal access the service is a trusted Service. If this field is null, principal is not a trusted service |
| Type | string | The name of the table |
| VaultProperties | dynamic | Detailed vault properties containing accesspolicy, iprule, virtualnetwork etc |
