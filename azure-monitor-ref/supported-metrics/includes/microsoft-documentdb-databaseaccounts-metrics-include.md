---
ms.service: azure-monitor
ms.topic: include
ms.date: 12/01/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DocumentDB/DatabaseAccounts, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Region Added**<p><p>Region Added |`AddRegion` |Count |Count |`Region`|PT5M |Yes|
|**Autoscaled RU**<p><p>Autoscaled RU consumption with Per Region and Per Partition Autoscale |`AutoscaledRU` |Count |Maximum |`DatabaseName`, `CollectionName`, `PhysicalPartitionId`, `Region`|PT1M, PT5M, PT1H, P1D |No|
|**Autoscale Max Throughput**<p><p>Autoscale Max Throughput |`AutoscaleMaxThroughput` |Count |Maximum |`DatabaseName`, `CollectionName`|PT5M, PT1H |No|
|**(deprecated) Available Storage**<p><p>"Available Storage"will be removed from Azure Monitor at the end of September 2023. Cosmos DB collection storage size is now unlimited. The only restriction is that the storage size for each logical partition key is 20GB. You can enable PartitionKeyStatistics in Diagnostic Log to know the storage consumption for top partition keys. For more info about Cosmos DB storage quota, please check this doc https://docs.microsoft.com/azure/cosmos-db/concepts-limits. After deprecation, the remaining alert rules still defined on the deprecated metric will be automatically disabled post the deprecation date. |`AvailableStorage` |Bytes |Total, Average |`CollectionName`, `DatabaseName`, `Region`|PT5M |No|
|**Cassandra Connection Closures**<p><p>Number of Cassandra connections that were closed, reported at a 1 minute granularity |`CassandraConnectionClosures` |Count |Average, Minimum, Maximum, Total |`APIType`, `Region`, `ClosureReason`|PT1M |No|
|**Cassandra Connector Average ReplicationLatency**<p><p>Cassandra Connector Average ReplicationLatency |`CassandraConnectorAvgReplicationLatency` |MilliSeconds |Average |\<none\>|PT5M |No|
|**Cassandra Connector Replication Health Status**<p><p>Cassandra Connector Replication Health Status |`CassandraConnectorReplicationHealthStatus` |Count |Count |`NotStarted`, `ReplicationInProgress`, `Error`|PT5M |No|
|**Cassandra Keyspace Created**<p><p>Cassandra Keyspace Created |`CassandraKeyspaceCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Cassandra Keyspace Deleted**<p><p>Cassandra Keyspace Deleted |`CassandraKeyspaceDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Cassandra Keyspace Throughput Updated**<p><p>Cassandra Keyspace Throughput Updated |`CassandraKeyspaceThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Cassandra Keyspace Updated**<p><p>Cassandra Keyspace Updated |`CassandraKeyspaceUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Cassandra Request Charges**<p><p>RUs consumed for Cassandra requests made |`CassandraRequestCharges` |Count |Total, Average, Minimum, Maximum |`APIType`, `DatabaseName`, `CollectionName`, `Region`, `OperationType`, `ResourceType`|PT1M |No|
|**Cassandra Requests**<p><p>Number of Cassandra requests made |`CassandraRequests` |Count |Count |`APIType`, `DatabaseName`, `CollectionName`, `Region`, `OperationType`, `ResourceType`, `ErrorCode`|PT1M |No|
|**Cassandra Table Created**<p><p>Cassandra Table Created |`CassandraTableCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Cassandra Table Deleted**<p><p>Cassandra Table Deleted |`CassandraTableDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Cassandra Table Throughput Updated**<p><p>Cassandra Table Throughput Updated |`CassandraTableThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Cassandra Table Updated**<p><p>Cassandra Table Updated |`CassandraTableUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Account Created**<p><p>Account Created |`CreateAccount` |Count |Count |\<none\>|PT5M |Yes|
|**Data Usage**<p><p>Total data usage reported at 5 minutes granularity |`DataUsage` |Bytes |Total, Average, Maximum, Minimum |`CollectionName`, `DatabaseName`, `Region`|PT5M, PT15M, PT30M, PT1H |No|
|**DedicatedGatewayAverageCPUUsage**<p><p>Average CPU usage across dedicated gateway instances |`DedicatedGatewayAverageCPUUsage` |Percent |Average |`Region`, `MetricType`|PT5M |No|
|**DedicatedGatewayAverageMemoryUsage**<p><p>Average memory usage across dedicated gateway instances, which is used for both routing requests and caching data |`DedicatedGatewayAverageMemoryUsage` |Bytes |Average |`Region`|PT5M |No|
|**DedicatedGatewayCPUUsage**<p><p>CPU usage across dedicated gateway instances |`DedicatedGatewayCPUUsage` |Percent |Average, Maximum, Minimum |`Region`, `ApplicationType`|PT1M |No|
|**DedicatedGatewayMaximumCPUUsage**<p><p>Average Maximum CPU usage across dedicated gateway instances |`DedicatedGatewayMaximumCPUUsage` |Percent |Average, Maximum |`Region`, `MetricType`|PT5M |No|
|**DedicatedGatewayMemoryUsage**<p><p>Memory usage across dedicated gateway instances |`DedicatedGatewayMemoryUsage` |Bytes |Average, Maximum, Minimum |`Region`, `ApplicationType`|PT1M |No|
|**DedicatedGatewayRequests**<p><p>Requests at the dedicated gateway |`DedicatedGatewayRequests` |Count |Count |`DatabaseName`, `CollectionName`, `CacheExercised`, `OperationName`, `Region`, `CacheHit`|PT1M |Yes|
|**Account Deleted**<p><p>Account Deleted |`DeleteAccount` |Count |Count |\<none\>|PT5M |Yes|
|**Document Count**<p><p>Total document count reported at 5 minutes, 1 hour and 1 day granularity |`DocumentCount` |Count |Total, Average |`CollectionName`, `DatabaseName`, `Region`|PT5M, PT1H, P1D |No|
|**Document Quota**<p><p>Total storage quota reported at 5 minutes granularity |`DocumentQuota` |Bytes |Total, Average |`CollectionName`, `DatabaseName`, `Region`|PT5M |No|
|**Gremlin Database Created**<p><p>Gremlin Database Created |`GremlinDatabaseCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Gremlin Database Deleted**<p><p>Gremlin Database Deleted |`GremlinDatabaseDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Gremlin Database Throughput Updated**<p><p>Gremlin Database Throughput Updated |`GremlinDatabaseThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Gremlin Database Updated**<p><p>Gremlin Database Updated |`GremlinDatabaseUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Gremlin Graph Created**<p><p>Gremlin Graph Created |`GremlinGraphCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Gremlin Graph Deleted**<p><p>Gremlin Graph Deleted |`GremlinGraphDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Gremlin Graph Throughput Updated**<p><p>Gremlin Graph Throughput Updated |`GremlinGraphThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Gremlin Graph Updated**<p><p>Gremlin Graph Updated |`GremlinGraphUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Gremlin Request Charges**<p><p>Request Units consumed for Gremlin requests made |`GremlinRequestCharges` |Count |Total, Average, Minimum, Maximum |`APIType`, `DatabaseName`, `CollectionName`, `Region`|PT1M |No|
|**Gremlin Requests**<p><p>Number of Gremlin requests made |`GremlinRequests` |Count |Count |`APIType`, `DatabaseName`, `CollectionName`, `Region`, `ErrorCode`|PT1M |No|
|**Index Usage**<p><p>Total index usage reported at 5 minutes granularity |`IndexUsage` |Bytes |Total, Average, Maximum, Minimum |`CollectionName`, `DatabaseName`, `Region`|PT5M, PT15M, PT30M, PT1H |No|
|**IntegratedCacheEvictedEntriesSize**<p><p>Size of the entries evicted from the integrated cache |`IntegratedCacheEvictedEntriesSize` |Bytes |Average |`Region`|PT5M |No|
|**IntegratedCacheItemExpirationCount**<p><p>Number of items evicted from the integrated cache due to TTL expiration |`IntegratedCacheItemExpirationCount` |Count |Average |`Region`, `CacheEntryType`|PT5M |No|
|**IntegratedCacheItemHitRate**<p><p>Number of point reads that used the integrated cache divided by number of point reads routed through the dedicated gateway with eventual consistency |`IntegratedCacheItemHitRate` |Percent |Average |`Region`, `CacheEntryType`|PT5M |No|
|**IntegratedCacheQueryExpirationCount**<p><p>Number of queries evicted from the integrated cache due to TTL expiration |`IntegratedCacheQueryExpirationCount` |Count |Average |`Region`, `CacheEntryType`|PT5M |No|
|**IntegratedCacheQueryHitRate**<p><p>Number of queries that used the integrated cache divided by number of queries routed through the dedicated gateway with eventual consistency |`IntegratedCacheQueryHitRate` |Percent |Average |`Region`, `CacheEntryType`|PT5M |No|
|**Materialized View Catchup Gap In Minutes**<p><p>Maximum time difference in minutes between data in source container and data propagated to materialized view |`MaterializedViewCatchupGapInMinutes` |Count |Maximum |`Region`, `TargetContainerName`, `BuildType`|PT1M |No|
|**Materialized Views Builder Average CPU Usage**<p><p>Average CPU usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderAverageCPUUsage` |Percent |Average |`Region`, `MetricType`|PT5M |No|
|**Materialized Views Builder Average Memory Usage**<p><p>Average memory usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderAverageMemoryUsage` |Bytes |Average |`Region`|PT5M |No|
|**Materialized Views Builder Maximum CPU Usage**<p><p>Average Maximum CPU usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderMaximumCPUUsage` |Percent |Average, Maximum |`Region`, `MetricType`|PT5M |No|
|**Metadata Requests**<p><p>Count of metadata requests. Cosmos DB maintains system metadata collection for each account, that allows you to enumerate collections, databases, etc, and their configurations, free of charge. |`MetadataRequests` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `Role`|PT1M |No|
|**Mongo Collection Created**<p><p>Mongo Collection Created |`MongoCollectionCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Mongo Collection Deleted**<p><p>Mongo Collection Deleted |`MongoCollectionDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Mongo Collection Throughput Updated**<p><p>Mongo Collection Throughput Updated |`MongoCollectionThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Mongo Collection Updated**<p><p>Mongo Collection Updated |`MongoCollectionUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Mongo Database Deleted**<p><p>Mongo Database Deleted |`MongoDatabaseDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Mongo Database Throughput Updated**<p><p>Mongo Database Throughput Updated |`MongoDatabaseThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Mongo Database Created**<p><p>Mongo Database Created |`MongoDBDatabaseCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Mongo Database Updated**<p><p>Mongo Database Updated |`MongoDBDatabaseUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Mongo Request Charge**<p><p>Mongo Request Units Consumed |`MongoRequestCharge` |Count |Total, Average, Maximum |`DatabaseName`, `CollectionName`, `Region`, `CommandName`, `ErrorCode`, `Status`|PT1M |Yes|
|**Mongo Requests**<p><p>Number of Mongo Requests Made |`MongoRequests` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `CommandName`, `ErrorCode`, `Status`|PT1M |Yes|
|**Normalized RU Consumption**<p><p>Max RU consumption percentage per minute |`NormalizedRUConsumption` |Percent |Maximum, Average |`CollectionName`, `DatabaseName`, `Region`, `PartitionKeyRangeId`, `CollectionRid`, `PhysicalPartitionId`, `OfferOwnerRid`|PT1M, PT5M, PT1H, P1D |No|
|**Region Offlined**<p><p>Region Offlined |`OfflineRegion` |Count |Count |`Region`, `StatusCode`, `Role`, `OperationName`|PT1M |No|
|**Region Onlined**<p><p>Region Onlined |`OnlineRegion` |Count |Count |`Region`, `StatusCode`, `Role`, `OperationName`|PT1M |No|
|**Physical Partition Count**<p><p>Physical Partition Count |`PhysicalPartitionCount` |Count |Count |`CollectionName`, `DatabaseName`, `IsSharedThroughputOffer`, `OfferOwnerRid`, `Region`|PT5M |Yes|
|**Physical Partition Size**<p><p>Physical Partition Size in bytes |`PhysicalPartitionSizeInfo` |Bytes |Maximum, Average |`CollectionName`, `DatabaseName`, `PhysicalPartitionId`, `OfferOwnerRid`, `Region`|PT1M, PT5M, PT1H, P1D |No|
|**Physical Partition Throughput**<p><p>Physical Partition Throughput |`PhysicalPartitionThroughputInfo` |Count |Maximum |`CollectionName`, `DatabaseName`, `PhysicalPartitionId`, `OfferOwnerRid`, `Region`|PT1M, PT5M, PT1H, P1D |No|
|**Provisioned Throughput**<p><p>Provisioned Throughput |`ProvisionedThroughput` |Count |Maximum |`DatabaseName`, `CollectionName`, `Region`|PT5M, PT1H, P1D |No|
|**Region Failed Over**<p><p>Region Failed Over |`RegionFailover` |Count |Count |\<none\>|PT5M |Yes|
|**Region Removed**<p><p>Region Removed |`RemoveRegion` |Count |Count |`Region`|PT5M |Yes|
|**P99 Replication Latency**<p><p>P99 Replication Latency across source and target regions for geo-enabled account |`ReplicationLatency` |MilliSeconds |Minimum, Maximum, Average |`SourceRegion`, `TargetRegion`|PT1M |Yes|
|**Server Side Latency**<p><p>Server Side Latency |`ServerSideLatency` |MilliSeconds |Average, Minimum, Maximum, Total |`DatabaseName`, `CollectionName`, `Region`, `ConnectionMode`, `OperationType`, `PublicAPIType`|PT1M, PT5M, PT1H, P1D |No|
|**Server Side Latency Direct**<p><p>Server Side Latency in Direct Connection Mode |`ServerSideLatencyDirect` |MilliSeconds |Average, Minimum, Maximum, Total, Percentile |`DatabaseName`, `CollectionName`, `Region`, `ConnectionMode`, `OperationType`, `PublicAPIType`, `APIType`|PT1M, PT5M, PT1H, P1D |No|
|**Server Side Latency Gateway**<p><p>Server Side Latency in Gateway Connection Mode |`ServerSideLatencyGateway` |MilliSeconds |Average, Minimum, Maximum, Total, Percentile |`DatabaseName`, `CollectionName`, `Region`, `ConnectionMode`, `OperationType`, `PublicAPIType`, `APIType`|PT1M, PT5M, PT1H, P1D |No|
|**Service Availability**<p><p>Account requests availability at one hour, day or month granularity |`ServiceAvailability` |Percent |Minimum, Average, Maximum |\<none\>|PT1H |No|
|**Sql Container Created**<p><p>Sql Container Created |`SqlContainerCreate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Sql Container Deleted**<p><p>Sql Container Deleted |`SqlContainerDelete` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Sql Container Throughput Updated**<p><p>Sql Container Throughput Updated |`SqlContainerThroughputUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Sql Container Updated**<p><p>Sql Container Updated |`SqlContainerUpdate` |Count |Count |`ResourceName`, `ChildResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Sql Database Created**<p><p>Sql Database Created |`SqlDatabaseCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Sql Database Deleted**<p><p>Sql Database Deleted |`SqlDatabaseDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**Sql Database Throughput Updated**<p><p>Sql Database Throughput Updated |`SqlDatabaseThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**Sql Database Updated**<p><p>Sql Database Updated |`SqlDatabaseUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**AzureTable Table Created**<p><p>AzureTable Table Created |`TableTableCreate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**AzureTable Table Deleted**<p><p>AzureTable Table Deleted |`TableTableDelete` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `OperationType`|PT5M |No|
|**AzureTable Table Throughput Updated**<p><p>AzureTable Table Throughput Updated |`TableTableThroughputUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`|PT5M |No|
|**AzureTable Table Updated**<p><p>AzureTable Table Updated |`TableTableUpdate` |Count |Count |`ResourceName`, `ApiKind`, `ApiKindResourceType`, `IsThroughputRequest`, `OperationType`|PT5M |No|
|**Total Requests**<p><p>Number of requests made |`TotalRequests` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `CapacityType`|PT1M |Yes|
|**Total Requests (Preview)**<p><p>Number of SQL requests |`TotalRequestsPreview` |Count |Count |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `PriorityLevel`, `IsExternal`|PT1M |No|
|**Total Request Units**<p><p>SQL Request Units consumed |`TotalRequestUnits` |Count |Total, Average, Maximum |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `CapacityType`|PT1M |Yes|
|**Total Request Units (Preview)**<p><p>Request Units consumed with CapacityType |`TotalRequestUnitsPreview` |Count |Total, Average, Maximum |`DatabaseName`, `CollectionName`, `Region`, `StatusCode`, `OperationType`, `Status`, `CapacityType`, `PriorityLevel`|PT1M |No|
|**Account Keys Updated**<p><p>Account Keys Updated |`UpdateAccountKeys` |Count |Count |`KeyType`|PT5M |Yes|
|**Account Network Settings Updated**<p><p>Account Network Settings Updated |`UpdateAccountNetworkSettings` |Count |Count |\<none\>|PT5M |Yes|
|**Account Replication Settings Updated**<p><p>Account Replication Settings Updated |`UpdateAccountReplicationSettings` |Count |Count |\<none\>|PT5M |Yes|
|**Account Diagnostic Settings Updated**<p><p>Account Diagnostic Settings Updated |`UpdateDiagnosticsSettings` |Count |Count |`DiagnosticSettingsName`, `ResourceGroupName`|PT5M |No|