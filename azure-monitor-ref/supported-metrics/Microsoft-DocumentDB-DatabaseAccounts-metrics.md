---
title: Supported metrics - Microsoft.DocumentDB/DatabaseAccounts
description: Reference for Microsoft.DocumentDB/DatabaseAccounts metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.DocumentDB/DatabaseAccounts  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.DocumentDB/DatabaseAccounts resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Region Added<p><p>Region Added |`AddRegion` |Count |Count |Region |Yes|
|Autoscale Max Throughput<p><p>Autoscale Max Throughput |`AutoscaleMaxThroughput` |Count |Maximum |DatabaseName, CollectionName |No|
|(deprecated) Available Storage<p><p>"Available Storage"will be removed from Azure Monitor at the end of September 2023. Cosmos DB collection storage size is now unlimited. The only restriction is that the storage size for each logical partition key is 20GB. You can enable PartitionKeyStatistics in Diagnostic Log to know the storage consumption for top partition keys. For more info about Cosmos DB storage quota, please check this doc https://docs.microsoft.com/azure/cosmos-db/concepts-limits. After deprecation, the remaining alert rules still defined on the deprecated metric will be automatically disabled post the deprecation date. |`AvailableStorage` |Bytes |Total |CollectionName, DatabaseName, Region |No|
|Cassandra Connection Closures<p><p>Number of Cassandra connections that were closed, reported at a 1 minute granularity |`CassandraConnectionClosures` |Count |Total |APIType, Region, ClosureReason |No|
|Cassandra Connector Average ReplicationLatency<p><p>Cassandra Connector Average ReplicationLatency |`CassandraConnectorAvgReplicationLatency` |MilliSeconds |Average |No Dimensions |No|
|Cassandra Connector Replication Health Status<p><p>Cassandra Connector Replication Health Status |`CassandraConnectorReplicationHealthStatus` |Count |Count |NotStarted, ReplicationInProgress, Error |No|
|Cassandra Keyspace Created<p><p>Cassandra Keyspace Created |`CassandraKeyspaceCreate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Cassandra Keyspace Deleted<p><p>Cassandra Keyspace Deleted |`CassandraKeyspaceDelete` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Cassandra Keyspace Throughput Updated<p><p>Cassandra Keyspace Throughput Updated |`CassandraKeyspaceThroughputUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Cassandra Keyspace Updated<p><p>Cassandra Keyspace Updated |`CassandraKeyspaceUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Cassandra Request Charges<p><p>RUs consumed for Cassandra requests made |`CassandraRequestCharges` |Count |Total |APIType, DatabaseName, CollectionName, Region, OperationType, ResourceType |No|
|Cassandra Requests<p><p>Number of Cassandra requests made |`CassandraRequests` |Count |Count |APIType, DatabaseName, CollectionName, Region, OperationType, ResourceType, ErrorCode |No|
|Cassandra Table Created<p><p>Cassandra Table Created |`CassandraTableCreate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Cassandra Table Deleted<p><p>Cassandra Table Deleted |`CassandraTableDelete` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Cassandra Table Throughput Updated<p><p>Cassandra Table Throughput Updated |`CassandraTableThroughputUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Cassandra Table Updated<p><p>Cassandra Table Updated |`CassandraTableUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Account Created<p><p>Account Created |`CreateAccount` |Count |Count |No Dimensions |Yes|
|Data Usage<p><p>Total data usage reported at 5 minutes granularity |`DataUsage` |Bytes |Total |CollectionName, DatabaseName, Region |No|
|DedicatedGatewayAverageCPUUsage<p><p>Average CPU usage across dedicated gateway instances |`DedicatedGatewayAverageCPUUsage` |Percent |Average |Region, MetricType |No|
|DedicatedGatewayAverageMemoryUsage<p><p>Average memory usage across dedicated gateway instances, which is used for both routing requests and caching data |`DedicatedGatewayAverageMemoryUsage` |Bytes |Average |Region |No|
|DedicatedGatewayCPUUsage<p><p>CPU usage across dedicated gateway instances |`DedicatedGatewayCPUUsage` |Percent |Average |Region, ApplicationType |No|
|DedicatedGatewayMaximumCPUUsage<p><p>Average Maximum CPU usage across dedicated gateway instances |`DedicatedGatewayMaximumCPUUsage` |Percent |Average |Region, MetricType |No|
|DedicatedGatewayMemoryUsage<p><p>Memory usage across dedicated gateway instances |`DedicatedGatewayMemoryUsage` |Bytes |Average |Region, ApplicationType |No|
|DedicatedGatewayRequests<p><p>Requests at the dedicated gateway |`DedicatedGatewayRequests` |Count |Count |DatabaseName, CollectionName, CacheExercised, OperationName, Region, CacheHit |Yes|
|Account Deleted<p><p>Account Deleted |`DeleteAccount` |Count |Count |No Dimensions |Yes|
|Document Count<p><p>Total document count reported at 5 minutes, 1 hour and 1 day granularity |`DocumentCount` |Count |Total |CollectionName, DatabaseName, Region |No|
|Document Quota<p><p>Total storage quota reported at 5 minutes granularity |`DocumentQuota` |Bytes |Total |CollectionName, DatabaseName, Region |No|
|Gremlin Database Created<p><p>Gremlin Database Created |`GremlinDatabaseCreate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Gremlin Database Deleted<p><p>Gremlin Database Deleted |`GremlinDatabaseDelete` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Gremlin Database Throughput Updated<p><p>Gremlin Database Throughput Updated |`GremlinDatabaseThroughputUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Gremlin Database Updated<p><p>Gremlin Database Updated |`GremlinDatabaseUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Gremlin Graph Created<p><p>Gremlin Graph Created |`GremlinGraphCreate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Gremlin Graph Deleted<p><p>Gremlin Graph Deleted |`GremlinGraphDelete` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Gremlin Graph Throughput Updated<p><p>Gremlin Graph Throughput Updated |`GremlinGraphThroughputUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Gremlin Graph Updated<p><p>Gremlin Graph Updated |`GremlinGraphUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Gremlin Request Charges<p><p>Request Units consumed for Gremlin requests made |`GremlinRequestCharges` |Count |Total |APIType, DatabaseName, CollectionName, Region |No|
|Gremlin Requests<p><p>Number of Gremlin requests made |`GremlinRequests` |Count |Count |APIType, DatabaseName, CollectionName, Region, ErrorCode |No|
|Index Usage<p><p>Total index usage reported at 5 minutes granularity |`IndexUsage` |Bytes |Total |CollectionName, DatabaseName, Region |No|
|IntegratedCacheEvictedEntriesSize<p><p>Size of the entries evicted from the integrated cache |`IntegratedCacheEvictedEntriesSize` |Bytes |Average |Region |No|
|IntegratedCacheItemExpirationCount<p><p>Number of items evicted from the integrated cache due to TTL expiration |`IntegratedCacheItemExpirationCount` |Count |Average |Region, CacheEntryType |No|
|IntegratedCacheItemHitRate<p><p>Number of point reads that used the integrated cache divided by number of point reads routed through the dedicated gateway with eventual consistency |`IntegratedCacheItemHitRate` |Percent |Average |Region, CacheEntryType |No|
|IntegratedCacheQueryExpirationCount<p><p>Number of queries evicted from the integrated cache due to TTL expiration |`IntegratedCacheQueryExpirationCount` |Count |Average |Region, CacheEntryType |No|
|IntegratedCacheQueryHitRate<p><p>Number of queries that used the integrated cache divided by number of queries routed through the dedicated gateway with eventual consistency |`IntegratedCacheQueryHitRate` |Percent |Average |Region, CacheEntryType |No|
|Materialized View Catchup Gap In Minutes<p><p>Maximum time difference in minutes between data in source container and data propagated to materialized view |`MaterializedViewCatchupGapInMinutes` |Count |Maximum |Region, TargetContainerName, BuildType |No|
|Materialized Views Builder Average CPU Usage<p><p>Average CPU usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderAverageCPUUsage` |Percent |Average |Region, MetricType |No|
|Materialized Views Builder Average Memory Usage<p><p>Average memory usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderAverageMemoryUsage` |Bytes |Average |Region |No|
|Materialized Views Builder Maximum CPU Usage<p><p>Average Maximum CPU usage across materialized view builder instances, which are used for populating data in materialized views |`MaterializedViewsBuilderMaximumCPUUsage` |Percent |Average |Region, MetricType |No|
|Metadata Requests<p><p>Count of metadata requests. Cosmos DB maintains system metadata collection for each account, that allows you to enumerate collections, databases, etc, and their configurations, free of charge. |`MetadataRequests` |Count |Count |DatabaseName, CollectionName, Region, StatusCode, Role |No|
|Mongo Collection Created<p><p>Mongo Collection Created |`MongoCollectionCreate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Mongo Collection Deleted<p><p>Mongo Collection Deleted |`MongoCollectionDelete` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Mongo Collection Throughput Updated<p><p>Mongo Collection Throughput Updated |`MongoCollectionThroughputUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Mongo Collection Updated<p><p>Mongo Collection Updated |`MongoCollectionUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Mongo Database Deleted<p><p>Mongo Database Deleted |`MongoDatabaseDelete` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Mongo Database Throughput Updated<p><p>Mongo Database Throughput Updated |`MongoDatabaseThroughputUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Mongo Database Created<p><p>Mongo Database Created |`MongoDBDatabaseCreate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Mongo Database Updated<p><p>Mongo Database Updated |`MongoDBDatabaseUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Mongo Request Charge<p><p>Mongo Request Units Consumed |`MongoRequestCharge` |Count |Total |DatabaseName, CollectionName, Region, CommandName, ErrorCode, Status |Yes|
|Mongo Requests<p><p>Number of Mongo Requests Made |`MongoRequests` |Count |Count |DatabaseName, CollectionName, Region, CommandName, ErrorCode, Status |Yes|
|Normalized RU Consumption<p><p>Max RU consumption percentage per minute |`NormalizedRUConsumption` |Percent |Maximum |CollectionName, DatabaseName, Region, PartitionKeyRangeId, CollectionRid, PhysicalPartitionId |No|
|Region Offlined<p><p>Region Offlined |`OfflineRegion` |Count |Count |Region, StatusCode, Role, OperationName |No|
|Region Onlined<p><p>Region Onlined |`OnlineRegion` |Count |Count |Region, StatusCode, Role, OperationName |No|
|Physical Partition Size<p><p>Physical Partition Size in bytes |`PhysicalPartitionSizeInfo` |Bytes |Maximum |CollectionName, DatabaseName, PhysicalPartitionId, OfferOwnerRid, Region |No|
|Physical Partition Throughput<p><p>Physical Partition Throughput |`PhysicalPartitionThroughputInfo` |Count |Maximum |CollectionName, DatabaseName, PhysicalPartitionId, OfferOwnerRid, Region |No|
|Provisioned Throughput<p><p>Provisioned Throughput |`ProvisionedThroughput` |Count |Maximum |DatabaseName, CollectionName, AllowWrite |No|
|Region Failed Over<p><p>Region Failed Over |`RegionFailover` |Count |Count |No Dimensions |Yes|
|Region Removed<p><p>Region Removed |`RemoveRegion` |Count |Count |Region |Yes|
|P99 Replication Latency<p><p>P99 Replication Latency across source and target regions for geo-enabled account |`ReplicationLatency` |MilliSeconds |Average |SourceRegion, TargetRegion |Yes|
|Server Side Latency<p><p>Server Side Latency |`ServerSideLatency` |MilliSeconds |Average |DatabaseName, CollectionName, Region, ConnectionMode, OperationType, PublicAPIType |No|
|Server Side Latency Direct<p><p>Server Side Latency in Direct Connection Mode |`ServerSideLatencyDirect` |MilliSeconds |Average |DatabaseName, CollectionName, Region, ConnectionMode, OperationType, PublicAPIType, APIType |No|
|Server Side Latency Gateway<p><p>Server Side Latency in Gateway Connection Mode |`ServerSideLatencyGateway` |MilliSeconds |Average |DatabaseName, CollectionName, Region, ConnectionMode, OperationType, PublicAPIType, APIType |No|
|Service Availability<p><p>Account requests availability at one hour, day or month granularity |`ServiceAvailability` |Percent |Average |No Dimensions |No|
|Sql Container Created<p><p>Sql Container Created |`SqlContainerCreate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Sql Container Deleted<p><p>Sql Container Deleted |`SqlContainerDelete` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Sql Container Throughput Updated<p><p>Sql Container Throughput Updated |`SqlContainerThroughputUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Sql Container Updated<p><p>Sql Container Updated |`SqlContainerUpdate` |Count |Count |ResourceName, ChildResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Sql Database Created<p><p>Sql Database Created |`SqlDatabaseCreate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Sql Database Deleted<p><p>Sql Database Deleted |`SqlDatabaseDelete` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|Sql Database Throughput Updated<p><p>Sql Database Throughput Updated |`SqlDatabaseThroughputUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|Sql Database Updated<p><p>Sql Database Updated |`SqlDatabaseUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|AzureTable Table Created<p><p>AzureTable Table Created |`TableTableCreate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|AzureTable Table Deleted<p><p>AzureTable Table Deleted |`TableTableDelete` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, OperationType |No|
|AzureTable Table Throughput Updated<p><p>AzureTable Table Throughput Updated |`TableTableThroughputUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest |No|
|AzureTable Table Updated<p><p>AzureTable Table Updated |`TableTableUpdate` |Count |Count |ResourceName, ApiKind, ApiKindResourceType, IsThroughputRequest, OperationType |No|
|Total Requests<p><p>Number of requests made |`TotalRequests` |Count |Count |DatabaseName, CollectionName, Region, StatusCode, OperationType, Status, CapacityType |Yes|
|Total Requests (Preview)<p><p>Number of SQL requests |`TotalRequestsPreview` |Count |Count |DatabaseName, CollectionName, Region, StatusCode, OperationType, Status, IsExternal |No|
|Total Request Units<p><p>SQL Request Units consumed |`TotalRequestUnits` |Count |Total |DatabaseName, CollectionName, Region, StatusCode, OperationType, Status, CapacityType |Yes|
|Total Request Units (Preview)<p><p>Request Units consumed with CapacityType |`TotalRequestUnitsPreview` |Count |Total |DatabaseName, CollectionName, Region, StatusCode, OperationType, Status, CapacityType, PriorityLevel |No|
|Account Keys Updated<p><p>Account Keys Updated |`UpdateAccountKeys` |Count |Count |KeyType |Yes|
|Account Network Settings Updated<p><p>Account Network Settings Updated |`UpdateAccountNetworkSettings` |Count |Count |No Dimensions |Yes|
|Account Replication Settings Updated<p><p>Account Replication Settings Updated |`UpdateAccountReplicationSettings` |Count |Count |No Dimensions |Yes|
|Account Diagnostic Settings Updated<p><p>Account Diagnostic Settings Updated |`UpdateDiagnosticsSettings` |Count |Count |DiagnosticSettingsName, ResourceGroupName |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->