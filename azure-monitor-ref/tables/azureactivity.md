---
title: Azure Monitor Logs reference - AzureActivity
description: Reference for AzureActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
---

# AzureActivity

Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure.

## Categories

- Azure Resources
- Audit
- Security
## Solutions

- LogManagement
## Resource types

- Azure AD Domain Services
- Microsoft App Configuration
- Application Gateways
- App Services
- Azure Autonomous Development Platform workspace
- Azure Attestation
- Azure Cache for Redis
- CDN Profiles
- Azure CloudHsm
- Communication Services
- Azure Cosmos DB
- Project CI Workspace
- Azure Digital Twins
- Event Grid Topics
- Event Hubs
- Firewalls
- Azure Managed Workspace for Grafana
- Key Vaults
- Kubernetes Services
- Azure Load Testing
- Azure Managed Instance for Apache Cassandra
- Nexus BareMetal Machines
- Nexus Clusters
- Nexus Storage Appliances
- Microsoft.Purview/accounts
- Recovery Services Vaults
- Relay
- Service Bus
- Azure Traffic Collector
- Azure Virtual Network Manager
- Bot Services
- Chaos Experiment
- Microsoft Connected Cache
- Microsoft Connected Vehicle Platform
- Network Watcher - Connection Monitor
- Container Apps
- Dynamics 365 Customer Insights
- Azure Database for MySQL Flexible Servers
- Azure Database for PostgreSQL Flexible Servers
- Dev Centers
- Experiment Workspace
- HDInsight Clusters
- Virtual machines
- Machine Learning
- Machine Learning
- Media Services
- Microsoft Graph Logs
- Azure Managed Lustre
- Azure Storage Mover
- Synapse Workspaces
- Desktop Virtualization Host Pools
- Default schema for a resource
- Azure Subscription
- Azure Resource Group
- SignalR Service WebPubSub
- Application Insights
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
- Load Balancers
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
| ActivityStatus | string |   |
| ActivityStatusValue | string | Status of the operation in display-friendly format. Common values include Started, In Progress, Succeeded, Failed, Active, Resolved. |
| ActivitySubstatus | string |   |
| ActivitySubstatusValue | string | Substatus of the operation  in display-friendly format. E.g. OK (HTTP Status Code: 200). |
| Authorization | string | Blob of RBAC properties of the event. Usually includes the “action”, “role” and “scope” properties. Stored as string. The use of Authorization_d should be preferred going forward. |
| Authorization_d | dynamic | Blob of RBAC properties of the event. Usually includes the “action”, “role” and “scope” properties. Stored as dynamic column. |
| _BilledSize | real | The record size in bytes |
| Caller | string | GUID of the caller. |
| CallerIpAddress | string | IP address of the user who has performed the operation UPN claim or SPN claim based on availability. |
| Category | string |   |
| CategoryValue | string | Category of the activity log e.g. Administrative, Policy, Security. |
| Claims | string | The JWT token used by Active Directory to authenticate the user or application to perform this operation in Resource Manager. The use of claims_d should be preferred going forward. |
| Claims_d | dynamic | The JWT token used by Active Directory to authenticate the user or application to perform this operation in Resource Manager. |
| CorrelationId | string | Usually a GUID in the string format. Events that share a correlationId belong to the same uber action. |
| EventDataId | string | Unique identifier of an event. |
| EventSubmissionTimestamp | datetime | Timestamp when the event became available for querying. |
| Hierarchy | string | Management group hierarchy of the management group or subscription that event belongs to. |
| HTTPRequest | string | Blob describing the Http Request. Usually includes the “clientRequestId”, “clientIpAddress” and “method” (HTTP method. For example, PUT). |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| Level | string | Level of the event. One of the following values: Critical, Error, Warning, Informational and Verbose. |
| OperationId | string | GUID of the operation |
| OperationName | string |   |
| OperationNameValue | string | Identifier of the operation e.g. Microsoft.Storage/storageAccounts/listAccountSas/action. |
| Properties | string | Set of <Key Value> pairs (i.e. Dictionary) describing the details of the event. Stored as string. Usage of Properties_d is recommended instead. |
| Properties_d | dynamic | Set of <Key Value> pairs (i.e. Dictionary) describing the details of the event. Stored as dynamic column. |
| Resource | string |   |
| ResourceGroup | string | Resource group name of the impacted resource. |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProvider | string |   |
| ResourceProviderValue | string | Id of the resource provider for the impacted resource - e.g. Microsoft.Storage. |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubscriptionId | string | Subscription ID of the impacted resource. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime | Timestamp when the event was generated by the Azure service processing the request corresponding the event. |
| Type | string | The name of the table |
