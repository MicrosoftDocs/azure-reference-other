---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 08/08/2024
ms.custom: Microsoft.DocumentDB/DatabaseAccounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Requests|**Region Added**<br><br>Region Added |`AddRegion` |Count |Count |`Region`|PT5M |Yes|
|Requests|**Autoscaled RU**<br><br>Autoscaled RU consumption with Per Region and Per Partition Autoscale |`AutoscaledRU` |Count |Maximum |`DatabaseName`, `CollectionName`, `PhysicalPartitionId`, `Region`|PT1M, PT5M, PT1H, P1D |No|
|Requests|**Autoscale Max Throughput**<br><br>Autoscale Max Throughput |`AutoscaleMaxThroughput` |Count |Maximum |`DatabaseName`, `CollectionName`|PT5M, PT1H |No|
|Requests|**(deprecated) Available Storage**<br><br>"Available Storage"will be removed from Azure Monitor at the end of September 2023. Cosmos DB collection storage size is now unlimited. The only restriction is that the storage size for each logical partition key is 20GB. You can enable PartitionKeyStatistics in Diagnostic Log to know the storage consumption for top partition keys. For more info about Cosmos DB storage quota, please check this doc /azure/cosmos-db/concepts-limits. After deprecation, the remaining alert rules still defined on the deprecated metric will be automatically disabled post the deprecation date. |`AvailableStorage` |Bytes |Total, Average |`CollectionName`, `DatabaseName`, `Region`|PT5M |No|
|Requests|**Cassandra Connection Closures**<br><br>Number of Cassandra connections that were closed, reported at a 1 minute granularity |`CassandraConnectionClosures` |Count |Average, Minimum, Maximum, Total |`APIType`, `Region`, `ClosureReason`|PT1M |No|
|Requests|**Cassandra Connector Average ReplicationLatency**<br><br>Cassandra Connector Average ReplicationLatency |`CassandraConnectorAvgReplicationLatency` |MilliSeconds |Average |\<none\>|PT5M |No|
|Requests|**Cassandra Connector Replication Health Status**<br><br>Cassandra Connector Replication Health Status |`CassandraConnectorReplicationHealthStatus` |Count |Count |`NotStarted`, `ReplicationInProgress`, `Error`|PT5M |No|
|Requests|**Cassandra Keyspace Created**<br><br>Cassandra Keyspace Created |`CassandraKeyspaceCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Cassandra Keyspace Deleted**<br><br>Cassandra Keyspace Deleted |`CassandraKeyspaceDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Cassandra Keyspace Throughput Updated**<br><br>Cassandra Keyspace Throughput Updated |`CassandraKeyspaceThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Cassandra Keyspace Updated**<br><br>Cassandra Keyspace Updated |`CassandraKeyspaceUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Cassandra Request Charges**<br><br>RUs consumed for Cassandra requests made |`CassandraRequestCharges` |Count |Total, Average, Minimum, Maximum |`APIType`, `DatabaseName`, `CollectionName`, `Region`, `OperationType`, `ResourceType`|PT1M |No|
|Requests|**Cassandra Requests**<br><br>Number of Cassandra requests made |`CassandraRequests` |Count |Count |`APIType`, `DatabaseName`, `CollectionName`, `Region`, `OperationType`, `ResourceType`, `ErrorCode`|PT1M |No|
|Requests|**Cassandra Table Created**<br><br>Cassandra Table Created |`CassandraTableCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Cassandra Table Deleted**<br><br>Cassandra Table Deleted |`CassandraTableDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Cassandra Table Throughput Updated**<br><br>Cassandra Table Throughput Updated |`CassandraTableThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Cassandra Table Updated**<br><br>Cassandra Table Updated |`CassandraTableUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Account Created**<br><br>Account Created |`CreateAccount` |Count |Count |\<none\>|PT5M |Yes|
|Requests|**Data Usage**<br><br>Total data usage reported at 5 minutes granularity |`DataUsage` |Bytes |Total, Average, Maximum, Minimum |`CollectionName`, `DatabaseName`, `Region`|PT5M, PT15M, PT30M, PT1H |No|
|Requests|**DedicatedGatewayAverageCPUUsage**<br><br>Average CPU usage across dedicated gateway instances |`DedicatedGatewayAverageCPUUsage` |Percent |Average |`Region`, `MetricType`|PT5M |No|
|Requests|**DedicatedGatewayAverageMemoryUsage**<br><br>Average memory usage across dedicated gateway instances, which is used for both routing requests and caching data |`DedicatedGatewayAverageMemoryUsage` |Bytes |Average |`Region`|PT5M |No|
|Requests|**DedicatedGatewayCPUUsage**<br><br>CPU usage across dedicated gateway instances |`DedicatedGatewayCPUUsage` |Percent |Average, Maximum, Minimum |`Region`, `ApplicationType`|PT1M |No|
|Requests|**DedicatedGatewayMaximumCPUUsage**<br><br>Average Maximum CPU usage across dedicated gateway instances |`DedicatedGatewayMaximumCPUUsage` |Percent |Average, Maximum |`Region`, `MetricType`|PT5M |No|
|Requests|**DedicatedGatewayMemoryUsage**<br><br>Memory usage across dedicated gateway instances |`DedicatedGatewayMemoryUsage` |Bytes |Average, Maximum, Minimum |`Region`, `ApplicationType`|PT1M |No|
|Requests|**DedicatedGatewayRequests**<br><br>Requests at the dedicated gateway |`DedicatedGatewayRequests` |Count |Count |`DatabaseName`, `CollectionName`, `CacheExercised`, `OperationName`, `Region`, `CacheHit`|PT1M |Yes|
|Requests|**Account Deleted**<br><br>Account Deleted |`DeleteAccount` |Count |Count |\<none\>|PT5M |Yes|
|Requests|**Document Count**<br><br>Total document count reported at 5 minutes, 1 hour and 1 day granularity |`DocumentCount` |Count |Total, Average |`CollectionName`, `DatabaseName`, `Region`|PT5M, PT1H, P1D |No|
|Requests|**Document Quota**<br><br>Total storage quota reported at 5 minutes granularity |`DocumentQuota` |Bytes |Total, Average |`CollectionName`, `DatabaseName`, `Region`|PT5M |No|
|Requests|**Gremlin Database Created**<br><br>Gremlin Database Created |`GremlinDatabaseCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Gremlin Database Deleted**<br><br>Gremlin Database Deleted |`GremlinDatabaseDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Gremlin Database Throughput Updated**<br><br>Gremlin Database Throughput Updated |`GremlinDatabaseThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Gremlin Database Updated**<br><br>Gremlin Database Updated |`GremlinDatabaseUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Gremlin Graph Created**<br><br>Gremlin Graph Created |`GremlinGraphCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Gremlin Graph Deleted**<br><br>Gremlin Graph Deleted |`GremlinGraphDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Gremlin Graph Throughput Updated**<br><br>Gremlin Graph Throughput Updated |`GremlinGraphThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Gremlin Graph Updated**<br><br>Gremlin Graph Updated |`GremlinGraphUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Gremlin Request Charges**<br><br>Request Units consumed for Gremlin requests made |`GremlinRequestCharges` |Count |Total, Average, Minimum, Maximum |`APIType`, `DatabaseName`, `CollectionName`, `Region`|PT1M |No|
|Requests|**Gremlin Requests**<br><br>Number of Gremlin requests made |`GremlinRequests` |Count |Count |`APIType`, `DatabaseName`, `CollectionName`, `Region`, `ErrorCode`|PT1M |No|
|Requests|**Index Usage**<br><br>Total index usage reported at 5 minutes granularity |`IndexUsage` |Bytes |Total, Average, Maximum, Minimum |`CollectionName`, `DatabaseName`, `Region`|PT5M, PT15M, PT30M, PT1H |No|
|Requests|**IntegratedCacheEvictedEntriesSize**<br><br>Size of the entries evicted from the integrated cache |`IntegratedCacheEvictedEntriesSize` |Bytes |Average |`Region`|PT5M |No|
|Requests|**IntegratedCacheItemExpirationCount**<br><br>Number of items evicted from the integrated cache due to TTL expiration |`IntegratedCacheItemExpirationCount` |Count |Average |`Region`, `CacheEntryType`|PT5M |No|
|Requests|**IntegratedCacheItemHitRate**<br><br>Number of point reads that used the integrated cache divided by number of point reads routed through the dedicated gateway with eventual consistency |`IntegratedCacheItemHitRate` |Percent |Average |`Region`, `CacheEntryType`|PT5M |No|
|Requests|**IntegratedCacheQueryExpirationCount**<br><br>Number of queries evicted from the integrated cache due to TTL expiration |`IntegratedCacheQueryExpirationCount` |Count |Average |`Region`, `CacheEntryType`|PT5M |No|
|Requests|**IntegratedCacheQueryHitRate**<br><br>Number of queries that used the integrated cache divided by number of queries routed through the dedicated gateway with eventual consistency |`IntegratedCacheQueryHitRate` |Percent |Average |`Region`, `CacheEntryType`|PT5M |No|
|Requests|**Materialized View Catchup Gap In Minutes**<br><br>Maximum time difference in minutes between data in source container and data propagated to materialized view |`MaterializedViewCatchupGapInMinutes` |Count |Maximum |`Region`, `TargetContainerName`, `BuildType`|PT1M |No|
|Requests|**Materialized Views Builder Average CPU Usage**<br><br>Average CPU usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderAverageCPUUsage` |Percent |Average |`Region`, `MetricType`|PT5M |No|
|Requests|**Materialized Views Builder Average Memory Usage**<br><br>Average memory usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderAverageMemoryUsage` |Bytes |Average |`Region`|PT5M |No|
|Requests|**Materialized Views Builder Maximum CPU Usage**<br><br>Average Maximum CPU usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderMaximumCPUUsage` |Percent |Average, Maximum |`Region`, `MetricType`|PT5M |No|
|Requests|**Metadata Requests**<br><br>Count of metadata requests. Cosmos DB maintains system metadata collection for each account, that allows you to enumerate collections, databases, etc, and their configurations, free of charge. |`MetadataRequests` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `Role`|PT1M |No|
|Requests|**Mongo Collection Created**<br><br>Mongo Collection Created |`MongoCollectionCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Mongo Collection Deleted**<br><br>Mongo Collection Deleted |`MongoCollectionDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Mongo Collection Throughput Updated**<br><br>Mongo Collection Throughput Updated |`MongoCollectionThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Mongo Collection Updated**<br><br>Mongo Collection Updated |`MongoCollectionUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Mongo Database Deleted**<br><br>Mongo Database Deleted |`MongoDatabaseDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Mongo Database Throughput Updated**<br><br>Mongo Database Throughput Updated |`MongoDatabaseThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Mongo Database Created**<br><br>Mongo Database Created |`MongoDBDatabaseCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Mongo Database Updated**<br><br>Mongo Database Updated |`MongoDBDatabaseUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Mongo Request Charge**<br><br>Mongo Request Units Consumed |`MongoRequestCharge` |Count |Total, Average, Maximum |`DatabaseName`, `CollectionName`, `Region`, `CommandName`, `ErrorCode`, `Status`|PT1M |Yes|
|Requests|**Mongo Requests**<br><br>Number of Mongo Requests Made |`MongoRequests` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `CommandName`, `ErrorCode`, `Status`|PT1M |Yes|
|Requests|**Normalized RU Consumption**<br><br>Max RU consumption percentage per minute |`NormalizedRUConsumption` |Percent |Maximum, Average |`CollectionName`, `DatabaseName`, `Region`, `PartitionKeyRangeId`, `CollectionRid`, `PhysicalPartitionId`, `OfferOwnerRid`|PT1M, PT5M, PT1H, P1D |No|
|Requests|**Region Offlined**<br><br>Region Offlined |`OfflineRegion` |Count |Count |`Region`, `StatusCode`, `Role`, `OperationName`|PT1M |No|
|Requests|**Region Onlined**<br><br>Region Onlined |`OnlineRegion` |Count |Count |`Region`, `StatusCode`, `Role`, `OperationName`|PT1M |No|
|Requests|**Physical Partition Count**<br><br>Physical Partition Count |`PhysicalPartitionCount` |Count |Maximum |`CollectionName`, `DatabaseName`, `IsSharedThroughputOffer`, `OfferOwnerRid`, `Region`|PT5M |Yes|
|Requests|**Physical Partition Size**<br><br>Physical Partition Size in bytes |`PhysicalPartitionSizeInfo` |Bytes |Maximum, Average |`CollectionName`, `DatabaseName`, `PhysicalPartitionId`, `OfferOwnerRid`, `Region`|PT1M, PT5M, PT1H, P1D |No|
|Requests|**Physical Partition Throughput**<br><br>Physical Partition Throughput |`PhysicalPartitionThroughputInfo` |Count |Maximum |`CollectionName`, `DatabaseName`, `PhysicalPartitionId`, `OfferOwnerRid`, `Region`|PT5M, PT1H, P1D |No|
|Requests|**Provisioned Throughput**<br><br>Provisioned Throughput |`ProvisionedThroughput` |Count |Maximum |`DatabaseName`, `CollectionName`, `Region`|PT5M, PT1H, P1D |No|
|Requests|**Region Failed Over**<br><br>Region Failed Over |`RegionFailover` |Count |Count |\<none\>|PT5M |Yes|
|Requests|**Region Removed**<br><br>Region Removed |`RemoveRegion` |Count |Count |`Region`|PT5M |Yes|
|Requests|**P99 Replication Latency**<br><br>P99 Replication Latency across source and target regions for geo-enabled account |`ReplicationLatency` |MilliSeconds |Minimum, Maximum, Average |`SourceRegion`, `TargetRegion`|PT1M |Yes|
|Requests|**(deprecated) Server Side Latency**<br><br>"Server Side Latency" will be removed from Azure Monitor at the end of August 2025. Please use "Server Side Latency Direct" and "Server Side Latency Gateway" to monitor the latency instead. For more info about latency metrics, please refer to this /azure/cosmos-db/monitor-server-side-latency. |`ServerSideLatency` |MilliSeconds |Average, Minimum, Maximum, Total |`DatabaseName`, `CollectionName`, `Region`, `ConnectionMode`, `OperationType`, `PublicAPIType`|PT1M, PT5M, PT1H, P1D |No|
|Requests|**Server Side Latency Direct**<br><br>Server Side Latency in Direct Connection Mode |`ServerSideLatencyDirect` |MilliSeconds |Average, Minimum, Maximum, Total |`DatabaseName`, `CollectionName`, `Region`, `ConnectionMode`, `OperationType`, `PublicAPIType`, `APIType`, `IsExternal`|PT1M, PT5M, PT1H, P1D |No|
|Requests|**Server Side Latency Gateway**<br><br>Server Side Latency in Gateway Connection Mode |`ServerSideLatencyGateway` |MilliSeconds |Average, Minimum, Maximum, Total |`DatabaseName`, `CollectionName`, `Region`, `ConnectionMode`, `OperationType`, `PublicAPIType`, `APIType`, `IsExternal`|PT1M, PT5M, PT1H, P1D |No|
|Requests|**Service Availability**<br><br>Account requests availability at one hour, day or month granularity |`ServiceAvailability` |Percent |Minimum, Average, Maximum |`IsExternal`|PT1H |No|
|Requests|**Sql Container Created**<br><br>Sql Container Created |`SqlContainerCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Sql Container Deleted**<br><br>Sql Container Deleted |`SqlContainerDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Sql Container Throughput Updated**<br><br>Sql Container Throughput Updated |`SqlContainerThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Sql Container Updated**<br><br>Sql Container Updated |`SqlContainerUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Sql Database Created**<br><br>Sql Database Created |`SqlDatabaseCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Sql Database Deleted**<br><br>Sql Database Deleted |`SqlDatabaseDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**Sql Database Throughput Updated**<br><br>Sql Database Throughput Updated |`SqlDatabaseThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**Sql Database Updated**<br><br>Sql Database Updated |`SqlDatabaseUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|SLI|**Success Rate (Preview)**<br><br>Percentage of successful requests processed |`SuccessRatePreview` |Percent |Average |`LocationId`|PT1M |No|
|Requests|**AzureTable Table Created**<br><br>AzureTable Table Created |`TableTableCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**AzureTable Table Deleted**<br><br>AzureTable Table Deleted |`TableTableDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|Requests|**AzureTable Table Throughput Updated**<br><br>AzureTable Table Throughput Updated |`TableTableThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|Requests|**AzureTable Table Updated**<br><br>AzureTable Table Updated |`TableTableUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|Requests|**Total Requests**<br><br>Number of requests made |`TotalRequests` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `CapacityType`, `PriorityLevel`, `ConnectionMode`, `IsExternal`|PT1M |No|
|Requests|**Total Requests (Preview)**<br><br>Number of SQL requests |`TotalRequestsPreview` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `PriorityLevel`, `IsExternal`|PT1M |No|
|Requests|**Total Request Units**<br><br>SQL Request Units consumed |`TotalRequestUnits` |Count |Total, Average, Maximum |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `CapacityType`, `PriorityLevel`|PT1M |Yes|
|Requests|**Total Request Units (Preview)**<br><br>Request Units consumed with CapacityType |`TotalRequestUnitsPreview` |Count |Total, Average, Maximum |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `CapacityType`, `PriorityLevel`|PT1M |No|
|Requests|**Account Keys Updated**<br><br>Account Keys Updated |`UpdateAccountKeys` |Count |Count |`KeyType`|PT5M |Yes|
|Requests|**Account Network Settings Updated**<br><br>Account Network Settings Updated |`UpdateAccountNetworkSettings` |Count |Count |\<none\>|PT5M |Yes|
|Requests|**Account Replication Settings Updated**<br><br>Account Replication Settings Updated |`UpdateAccountReplicationSettings` |Count |Count |\<none\>|PT5M |Yes|
|Requests|**Account Diagnostic Settings Updated**<br><br>Account Diagnostic Settings Updated |`UpdateDiagnosticsSettings` |Count |Count |`DiagnosticSettingsName`, `ResourceGroupName`|PT5M |No|