---
title: Azure Monitor Logs reference - AzureMetrics
description: Reference for AzureMetrics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# AzureMetrics

Metric data emitted by Azure services that measure their health and performance.

## Categories

- Azure Resources
## Solutions

- LogManagement
## Resource types

- Azure AD Domain Services
- Application Gateways
- App Services
- Azure Cache for Redis
- Azure CloudHsm
- Communication Services
- Azure Cosmos DB
- Project CI Workspace
- Event Grid Topics
- Event Hubs
- Firewalls
- Key Vaults
- Kubernetes Services
- Nexus BareMetal Machines
- Nexus Clusters
- Nexus Storage Appliances
- Relay
- Service Bus
- Azure Traffic Collector
- Azure Virtual Network Manager
- Microsoft Connected Cache
- Microsoft Connected Vehicle Platform
- Azure Database for MySQL Flexible Servers
- Azure Database for PostgreSQL Flexible Servers
- Dev Centers
- Virtual machines
- Machine Learning
- Media Services
- Azure Managed Lustre
- Azure Storage Mover
- Synapse Workspaces
- Desktop Virtualization Host Pools
- Desktop Virtualization Application Groups
- Desktop Virtualization workspaces
- Time Series Insights Environments
- Workload Monitor
- Analysis Services
- Batch Accounts
- Azure Spring Apps
- Cognitive Services
- Storage Accounts
- SignalR
- Container Registries
- Azure Data Explorer Clusters
- Azure Blockchain Service
- Event Grid Domains
- Event Grid Partner Namespaces
- Event Grid Partner Topics
- Event Grid System Topics
- VMware
- Azure Stack HCI
- System Center Virtual Machine Manager
- Virtual Machine Scale Sets
- Azure Arc Enabled Kubernetes
- Azure Arc Provisioned Clusters
- Azure Databricks Services
- Azure Monitor autoscale settings
- IoT Hub
- Service Fabric Clusters
- Logic Apps
- API Management services
- Automation account
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
- Azure Database for MariaDB Servers
- Device Provisioning Services
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
- Azure API for FHIR




## Columns

| Column | Type | Description |
|---|---|---|
| Average | real |   |
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
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
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
| ResourceId | string | Resource ID of the Azure resource reporting the metric. Same as _ResourceId present for backward compatibility reasons. _ResourceId should be used |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProvider | string | Resource provider of the Azure resource reporting the metric. |
| ResultDescription | string | Deprecated |
| ResultSignature | string | Deprecated |
| ResultType | string | Reduces the set of data collected. The syntax allowed depends on the operation. See the operation's description for details. |
| Severity | int | Deprecated |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubscriptionId | string | Subscription id of the Azure resource reporting the metric. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TimeGenerated | datetime | Date and time the record was created. |
| TimeGrain | string | Time grain of the metric e.g. PT1M |
| TLPLevel | string | Deprecated |
| Total | real | Sum of all of the values in the time range. |
| Type | string | The name of the table |
| UnitName | string | Unit of the metric. Examples include Seconds Percent Bytes. |
