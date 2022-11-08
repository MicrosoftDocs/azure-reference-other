---
title: Azure Monitor Logs reference - CDBControlPlaneRequests
description: Reference for CDBControlPlaneRequests table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 11/3/2022
---

# CDBControlPlaneRequests

 This table details all control plane operations executed on the account, which include modifications to the regional failover policy, indexing policy, IAM role assignments, backup/restore policies, VNet and firewall rules, private links as well as updates and deletes of the account.

## Solutions

- LogManagement
## Resource types

- Azure Cosmos DB




## Columns

| Column | Type | Description |
| --- | --- | --- |
| AccountName | string | The name of the Cosmos DB account. |
| AcledSubnets | string | The ACL’d subnets for the account. |
| ActivityId | string | The Activity ID of the operation. |
| ApiKind | string | The API kind for the account (SQL, Graph, Mongo, Cassanda, Table) that is specified during account creation. |
| ApiKindResourceType | string | The resource against which this Control Plane operation was executed (e.g. Database, Container etc.) |
| AssociatedRoleDefinitionId | string | The ID of the IAM role definition for the IAM role created for the account. |
| BackupIntervalInMinutes | real | The time (in minutes) between consecutive backup snapshots for the Cosmos DB account. |
| BackupRetentionIntervalInHours | real | The duration of time (in hours) for which backup snapshots are retained for the Cosmos DB account. |
| Cors | string | Collection of account’s Cross Origin Resource Sharing Rules |
| CurrentWriteRegion | string | The current write region for this account (applies when a regional failover is triggered to choose a new write region). |
| DefaultConsistencyLevel | string | The default consistency level for the Cosmos DB account. |
| DurationMs | real | The time taken (in milliseconds) for this control plane operation to complete. |
| EnableAutomaticFailover | bool | Boolean flag to enable automatic failover for the Cosmos DB account. |
| EnableCassandraRequestsTrace | bool | Boolean flag indicating if diagnostic logs are enabled for all Cassandra API operations. |
| EnableControlPlaneRequestsTrace | bool | Boolean flag indicting if diagnostic logs are enabled for Control Plane operations. |
| EnableDataPlaneRequestsTrace | bool | Boolean flag indicating if diagnostic logs are enabled for all Data Plane Operations. |
| EnableGremlinRequestsTrace | bool | Boolean flag indicating if diagnostic logs are enabled for Gremlin operations. |
| EnableMongoRequestsTrace | bool | Boolean flag indicating if diagnostic logs are enabled for all Mongo API operations. |
| EnablePrivateEndpointConnection | bool | Boolean flag to enable private endpoints for the Cosmos DB account. |
| EnableVirtualNetworkFilter | bool | Boolean flag indicating if VNet filters were enabled for the account. |
| HttpMethod | string | The HTTP method issued for this control plane operation. |
| HttpStatusCode | int | The HTTP status code of the control plane operation. |
| IpRangeFilter | string | The IP range filter specified as part of the VNet rules for the Cosmos DB account. |
| MaxStalenessIntervalInSeconds | real | The maximum staleness value (in seconds) for the Cosmos DB account when using the Bounded Staleness consistency setting. |
| MaxStalenessPrefix | string | The max staleness prefix for the Cosmos DB account when using the Bounded Staleness consistency setting. |
| MultipleWriteLocations | bool | Boolean flag indicating if the Cosmos DB account is a multi-master account. |
| NewWriteRegion | string | The new write region for the Cosmos DB account (after a user-initiated failover operation is executed). |
| OperationName | string | The Control Plane Operation that was executed. |
| OperationType | string | The type of control plane operation, which was executed. Examples of operations included Add/Remove region, Indexing Policy updates, VNet and firewall rule creation, Backup Retention Policy changes etc. |
| PrivateEndpointArmUrl | string | The ARM URL of the private endpoint created for the account. |
| PrivateEndpointConnections | string | The list of private endpoints for the Cosmos DB account (in each region). |
| RegionName | string | The region in which this control plan operation was executed. |
| ResourceDetails | string | The specific resource within the account against which the Control Plane Operation was executed. For e.g. the index for the container for which the indexing policy was created or updated. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceUri | string | The URI of the Cosmos DB resource (e.g. Database, Container) against which the control plane operation was execution. |
| Result | string | The result of the operation indicating either success or failure. |
| RoleAssignmentId | string | The role assignment Id for the IAM role created for the account. |
| RoleAssignmentPrincipalId | string | The Principal ID associated with the IAM Role Assignment created for the account. |
| RoleAssignmentPrincipalType | string | The Principal type of the IAM role assignment created for the account. |
| RoleAssignmentScope | string | The scope of access for the IAM role created for the account. |
| RoleDefinitionAssignableScopes | string | The assignable scopes for the IAM role created for the account. |
| RoleDefinitionId | string | The Id of the IAM role created for the account. |
| RoleDefinitionName | string | The name of the IAM role created for the account. |
| RoleDefinitionPermissions | string | The permissions associated with the IAM role created for the account. |
| RoleDefinitionType | string | The type of IAM role created for the account. |
| SourceSystem | string |  |
| SqlQueryTextTraceType | bool | Boolean flag indicating if full query text logging is enabled. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string |  |
| TimeGenerated | datetime | Timestamp (in UTC) when this Control Plane operation was executed against the Cosmos DB account. |
| Type | string | The name of the table |
| VirtualNetworkName | string | The name of the Vnet for the account. |
| VirtualNetworkResourceEntries | string | The list of IP addresses being included as part of the VNet rule for the account. |
| VnetArmUrl | string | The ARM URL for the VNet for the account. |
| VnetDatabaseAccountEntries | string | The list of virtual networks specified for the account. |
| VnetLocation | string | The Azure region in which the VNet for the account is location. |
| VnetResourceGroupName | string | The name of the resource group within which the VNet is created. |
