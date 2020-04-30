---
title: Azure Monitor Logs reference - AzureMetrics
description: Reference for AzureMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 4/30/2020
---

# AzureMetrics

 Metric data emitted by Azure services that measure their health and performance.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Analysis Services
- Power BI Dedicated
- Data Share
- SQL Managed instance
- SQL server
- SQL database
- Azure Database for MySQL server
- Azure Database for PostgreSQL server
- Azure Database for PostgreSQL server
- Azure Database for MariaDB server
- Device Provisioning Services
- Event Hub
- Application Gateway
- Firewall
- ExpressRoute circuit
- Front Door
- Load balancer
- Network interface
- Network security group
- Public IP addresses
- Traffic Manager profile
- Virtual network gateway
- Virtual network
- Search Services
- Stream Analytics
- Bastion
- Data Lake Analytics
- Azure API for FHIR
- Data Lake Storage Gen1
- Automation account
- Batch account
- Azure Spring Cloud
- Media Services
- Azure Cache for Redis
- Cognitive Services
- Key vault
- App Service
- Storage account
- SignalR
- Container registry
- Azure Data Explorer cluster
- Azure AD Domain Services
- Azure Blockchain service
- Event Grid domain
- Virtual machine
- Virtual machine scale set
- Kubernetes Services
- Azure Databricks Services
- Azure Monitor autoscale settings
- IoT Hub
- Azure Cosmos DB account
- Machine Learning
- Service Fabric cluster
- Logic App
- API Management services
- Data factory (V2)
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
|_ResourceId|string||
|ResourceId|string|Resource ID of the Azure resource reporting the metric. Same as _ResourceId present for backward compatibility reasons. _ResourceId should be used|
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
|Type|string||
|UnitName|string|Unit of the metric. Examples include Seconds Percent Bytes.|
