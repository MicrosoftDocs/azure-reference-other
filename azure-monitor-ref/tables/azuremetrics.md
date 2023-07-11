---
title: Azure Monitor Logs reference - AzureMetrics
description: Reference for AzureMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 7/10/2023
---

# AzureMetrics

 Metric data emitted by Azure services that measure their health and performance.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure AD Domain Services
- Data Lake Storage Gen1
- Data factories
- Automation account
- API Management services
- Logic Apps
- Service Fabric Clusters
- IoT Hub
- Azure Monitor autoscale settings
- Data Lake Analytics
- Azure Databricks Services
- Azure Arc Enabled Kubernetes
- Virtual Machine Scale Sets
- System Center Virtual Machine Manager
- Azure Stack HCI
- VMware
- Event Grid System Topics
- Event Grid Partner Topics
- Event Grid Partner Namespaces
- Azure Arc Provisioned Clusters
- Event Grid Domains
- Power BI Embedded
- SQL Managed Instances
- Stream Analytics jobs
- Search Services
- Virtual Networks
- Virtual Private Network Gateways
- Virtual Network Gateways
- Traffic Manager Profiles
- Public IP Addresses
- Network Security Groups
- Data Share
- Network Interfaces
- ExpressRoute Circuits
- Device Provisioning Services
- Azure Database for MariaDB Servers
- Azure Database for PostgreSQL Servers V2
- Azure Database for PostgreSQL Servers
- Azure Database for MySQL Servers
- SQL Databases
- SQL Servers
- Front Doors
- Azure Blockchain Service
- Azure Data Explorer Clusters
- Container Registries
- Azure Traffic Collector
- Service Bus
- Relay
- Nexus Storage Appliances
- Nexus Clusters
- Nexus BareMetal Machines
- Kubernetes Services
- Key Vaults
- Azure Virtual Network Manager
- Firewalls
- Event Grid Topics
- Project CI Workspace
- Azure Cosmos DB
- Communication Services
- Azure CloudHsm
- Azure Cache for Redis
- App Services
- Application Gateways
- Event Hubs
- Microsoft Connected Cache
- Microsoft Connected Vehicle Platform
- Azure Database for MySQL Flexible Servers
- SignalR
- Storage Accounts
- Cognitive Services
- Azure Spring Cloud
- Batch Accounts
- Analysis Services
- Workload Monitor
- Time Series Insights Environments
- Desktop Virtualization workspaces
- Desktop Virtualization Application Groups
- Desktop Virtualization Host Pools
- Synapse Workspaces
- Azure Storage Mover
- Azure Managed Lustre
- Media Services
- Machine Learning
- Virtual machines
- Dev Centers
- Azure Database for PostgreSQL Flexible Servers
- Bastions
- Azure API for FHIR




## Columns

| Column | Type | Description |
| --- | --- | --- |
| Average | real |  |
| _BilledSize | real | The record size in bytes |
| CallerIpAddress | string | Deprecated |
| Category | string | Deprecated |
| Confidence | string | Deprecated |
| CorrelationId | string | Deprecated |
| Count | real | Number of samples collected during the time range. Can be used to determine the number of values that contributed to the average value. |
| Description | string | Deprecated |
| DurationMs | long | Deprecated |
| FirstReportedDateTime | string | Deprecated |
| IndicatorThreatType | string | Deprecated |
| IsActive | string | Deprecated |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is *false* ingestion isn't billed to your Azure account |
| LastReportedDateTime | string | Deprecated |
| MaliciousIP | string | Deprecated |
| Maximum | real | Maximum value collected during in the time range. |
| MetricName | string | Display name of the metric. |
| Minimum | real | Minimum value collected during in the time range. |
| OperationName | string | Deprecated |
| OperationVersion | string | Deprecated |
| RemoteIPCountry | string | Deprecated |
| RemoteIPLatitude | real | Deprecated |
| RemoteIPLongitude | real | Deprecated |
| Resource | string | Resource name of the Azure resource reporting the metric. |
| ResourceGroup | string | Resource group name of the Azure resource reporting the metric. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string | Resource ID of the Azure resource reporting the metric. Same as _ResourceId present for backward compatibility reasons. _ResourceId should be used |
| ResourceProvider | string | Resource provider of the Azure resource reporting the metric. |
| ResultDescription | string | Deprecated |
| ResultSignature | string | Deprecated |
| ResultType | string | Reduces the set of data collected. The syntax allowed depends on the operation. See the operation's description for details. |
| Severity | int | Deprecated |
| SourceSystem | string | The type of agent the event was collected by. For example, *OpsManager* for Windows agent, either direct connect or Operations Manager, *Linux* for all Linux agents, or *Azure* for Azure Diagnostics |
| SubscriptionId | string | Subscription id of the Azure resource reporting the metric. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TimeGrain | string | Time grain of the metric e.g. PT1M |
| TLPLevel | string | Deprecated |
| Total | real | Sum of all of the values in the time range. |
| Type | string | The name of the table |
| UnitName | string | Unit of the metric. Examples include Seconds Percent Bytes. |
