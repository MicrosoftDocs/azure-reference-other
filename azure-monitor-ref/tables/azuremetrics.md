---
title: Azure Monitor Logs reference - AzureMetrics
description: Reference for AzureMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/9/2020
---

# AzureMetrics

 Metric data emitted by Azure services that measure their health and performance.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- App Services
- Data factories
- Data Lake Storage Gen1
- Data Lake Analytics
- Power BI Embedded
- Data Share
- SQL Managed Instances
- SQL Servers
- SQL Databases
- Azure Database for MySQL Servers
- Azure Database for PostgreSQL Servers
- Azure Database for PostgreSQL Servers V2
- Azure Database for PostgreSQL Flexible Servers
- Azure Database for MariaDB Servers
- Device Provisioning Services
- Event Hubs
- Application Gateways
- Firewalls
- ExpressRoute Circuits
- Front Doors
- Network Interfaces
- Network Security Groups
- Public IP Addresses
- Traffic Manager Profiles
- Virtual Network Gateways
- Virtual Private Network Gateways
- Virtual Networks
- Search Services
- Stream Analytics jobs
- Bastions
- Automation account
- Azure API for FHIR
- API Management services
- Service Fabric Clusters
- Desktop Virtualization Application Groups
- Desktop Virtualization Host Pools
- Desktop Virtualization workspaces
- Time Series Insights Environments
- Event Grid Topics
- Workload Monitor
- Analysis Services
- Batch Accounts
- Azure Spring Cloud
- Media Services
- Azure Cache for Redis
- Cognitive Services
- Key Vaults
- Storage Accounts
- SignalR
- Container Registries
- Azure Data Explorer Clusters
- Azure AD Domain Services
- Azure Blockchain Service
- Event Grid Domains
- Virtual machines
- Virtual Machine Scale Sets
- Kubernetes Services
- Azure Arc enabled Kubernetes
- Azure Databricks Services
- Azure Monitor autoscale settings
- IoT Hub
- Azure Cosmos DB
- Machine Learning
- Logic Apps
- Service Bus




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
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceId|string|Resource ID of the Azure resource reporting the metric. Same as _ResourceId present for backward compatibility reasons. _ResourceId should be used|
|ResourceProvider|string|Resource provider of the Azure resource reporting the metric.|
|ResultDescription|string|Deprecated|
|ResultSignature|string|Deprecated|
|ResultType|string|Reduces the set of data collected. The syntax allowed depends on the operation. See the operation's description for details.|
|Severity|int|Deprecated|
|SourceSystem|string|OpsManagerfor all records in this table.|
|SubscriptionId|string|Subscription id of the Azure resource reporting the metric.|
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|TimeGenerated|datetime|Date and time the record was created.|
|TimeGrain|string|Time grain of the metric e.g. PT1M|
|TLPLevel|string|Deprecated|
|Total|real|Sum of all of the values in the time range.|
|Type|string|The name of the table|
|UnitName|string|Unit of the metric. Examples include Seconds Percent Bytes.|
