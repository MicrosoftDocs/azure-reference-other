---
title: Azure Monitor Logs reference - AzureMetrics
description: Reference for AzureMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# AzureMetrics

 Metric data emitted by Azure services that measure their health and performance.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure Database for PostgreSQL Servers
- Azure Database for PostgreSQL Servers V2
- SQL Databases
- Azure Database for MySQL Servers
- Device Provisioning Services
- Event Hubs
- Azure Database for PostgreSQL Flexible Servers
- Azure Database for MariaDB Servers
- Data Lake Storage Gen1
- Data Lake Analytics
- Automation account
- Data factories
- SQL Managed Instances
- SQL Servers
- Power BI Embedded
- Data Share
- Virtual Networks
- Search Services
- Virtual Network Gateways
- Virtual Private Network Gateways
- Azure API for FHIR
- Service Bus
- Stream Analytics jobs
- Bastions
- ExpressRoute Circuits
- Front Doors
- Application Gateways
- Firewalls
- Public IP Addresses
- Traffic Manager Profiles
- Network Interfaces
- Network Security Groups
- Azure Cache for Redis
- Cognitive Services
- Azure Spring Cloud
- Media Services
- Storage Accounts
- SignalR
- Key Vaults
- App Services
- Desktop Virtualization workspaces
- Time Series Insights Environments
- Desktop Virtualization Application Groups
- Desktop Virtualization Host Pools
- Analysis Services
- Batch Accounts
- Event Grid Topics
- Workload Monitor
- IoT Hub
- Azure Cosmos DB
- Azure Databricks Services
- Azure Monitor autoscale settings
- Logic Apps
- API Management services
- Machine Learning
- Service Fabric Clusters
- Azure AD Domain Services
- Azure Blockchain Service
- Container Registries
- Azure Data Explorer Clusters
- Virtual Machine Scale Sets
- Kubernetes Services
- Event Grid Domains
- Virtual machines




## Columns

|Column|Type|Description|
|---|---|---|
|Average|real||
|CallerIpAddress|string|Deprecated|
|Category|string|Deprecated|
|Confidence|string|Deprecated|
|CorrelationId|string|Deprecated|
|Count|real|Number of samples collected during the time range. Can be used to determine the number of values that contributed to the average value.|
|Description|string|Deprecated|
|DurationMs|long|Deprecated|
|FirstReportedDateTime|string|Deprecated|
|IndicatorThreatType|string|Deprecated|
|IsActive|string|Deprecated|
|LastReportedDateTime|string|Deprecated|
|MaliciousIP|string|Deprecated|
|Maximum|real|Maximum value collected during in the time range.|
|MetricName|string|Display name of the metric.|
|Minimum|real|Minimum value collected during in the time range.|
|OperationName|string|Deprecated|
|OperationVersion|string|Deprecated|
|RemoteIPCountry|string|Deprecated|
|RemoteIPLatitude|real|Deprecated|
|RemoteIPLongitude|real|Deprecated|
|Resource|string|Resource name of the Azure resource reporting the metric.|
|ResourceGroup|string|Resource group name of the Azure resource reporting the metric.|
|ResourceId|string|Resource ID of the Azure resource reporting the metric. Same as _ResourceId present for backward compatibility reasons. _ResourceId should be used|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceProvider|string|Resource provider of the Azure resource reporting the metric.|
|ResultDescription|string|Deprecated|
|ResultSignature|string|Deprecated|
|ResultType|string|Reduces the set of data collected. The syntax allowed depends on the operation. See the operation's description for details.|
|Severity|int|Deprecated|
|SourceSystem|string|OpsManagerfor all records in this table.|
|SubscriptionId|string|Subscription id of the Azure resource reporting the metric.|
|TimeGenerated|datetime|Date and time the record was created.|
|TimeGrain|string|Time grain of the metric e.g. PT1M|
|TLPLevel|string|Deprecated|
|Total|real|Sum of all of the values in the time range.|
|Type|string|The name of the table|
|UnitName|string|Unit of the metric. Examples include Seconds Percent Bytes.|
