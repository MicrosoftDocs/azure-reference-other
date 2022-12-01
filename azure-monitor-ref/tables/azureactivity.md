---
title: Azure Monitor Logs reference - AzureActivity
description: Reference for AzureActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 12/1/2022
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

- Microsoft App Configuration
- Data Lake Analytics
- Data Lake Storage Gen1
- Recovery Services Vaults
- Data factories
- Automation account
- API Management services
- Logic Apps
- Service Fabric Clusters
- IoT Hub
- Azure Monitor autoscale settings
- Azure Databricks Services
- Azure Arc enabled Kubernetes
- Virtual Machine Scale Sets
- System Center Virtual Machine Manager
- Azure Stack HCI
- VMware
- Event Grid System Topics
- Event Grid Partner Topics
- Event Grid Partner Namespaces
- Event Grid Domains
- Azure Blockchain Service
- Power BI Embedded
- Azure AD Domain Services
- Data Share
- SQL Servers
- Bastions
- Stream Analytics jobs
- Search Services
- Virtual Networks
- Virtual Private Network Gateways
- Virtual Network Gateways
- Traffic Manager Profiles
- Public IP Addresses
- Network Security Groups
- Network Interfaces
- Load Balancers
- Front Doors
- ExpressRoute Circuits
- Application Gateways
- Event Hubs
- Device Provisioning Services
- Azure Database for MariaDB Servers
- Azure Database for PostgreSQL Servers V2
- Azure Database for PostgreSQL Servers
- Azure Database for MySQL Servers
- SQL Databases
- SQL Managed Instances
- Azure API for FHIR
- Azure Data Explorer Clusters
- SignalR
- Network Watcher - Connection Monitor
- Microsoft Connected Vehicle Platform
- Microsoft Connected Cache
- Bot Services
- Azure Traffic Collector
- Microsoft.Purview/accounts
- Kubernetes Services
- Azure Managed Instance for Apache Cassandra
- Azure Load Testing
- Key Vaults
- Azure Managed Workspace for Grafana
- Firewalls
- Event Grid Topics
- Azure Digital Twins
- Project CI Workspace
- Azure Cosmos DB
- Communication Services
- Azure Cache for Redis
- Azure Attestation
- Azure Autonomous Development Platform workspace
- App Services
- Container Apps
- Container Registries
- Dynamics 365 Customer Insights
- Experiment Workspace
- Storage Accounts
- Cognitive Services
- Azure Spring Cloud
- CDN Profiles
- Batch Accounts
- Analysis Services
- Workload Monitor
- Time Series Insights Environments
- Desktop Virtualization workspaces
- Desktop Virtualization Application Groups
- Application Insights
- SignalR Service WebPubSub
- Azure Resource Group
- Azure Subscription
- Default schema for a resource
- Desktop Virtualization Host Pools
- Synapse Workspaces
- Virtual machines
- Media Services
- Machine Learning
- HDInsight Clusters
- Azure Database for PostgreSQL Flexible Servers
- Service Bus




## Columns

| Column | Type | Description |
| --- | --- | --- |
| ActivityStatus | string |  |
| ActivityStatusValue | string | Status of the operation in display-friendly format. Common values include Started, In Progress, Succeeded, Failed, Active, Resolved. |
| ActivitySubstatus | string |  |
| ActivitySubstatusValue | string | Substatus of the operation  in display-friendly format. E.g. OK (HTTP Status Code: 200). |
| Authorization | string | Blob of RBAC properties of the event. Usually includes the “action”, “role” and “scope” properties. Stored as string. The use of Authorization_d should be preferred going forward. |
| Authorization_d | dynamic | Blob of RBAC properties of the event. Usually includes the “action”, “role” and “scope” properties. Stored as dynamic column. |
| Caller | string | GUID of the caller. |
| CallerIpAddress | string | IP address of the user who has performed the operation UPN claim or SPN claim based on availability. |
| Category | string |  |
| CategoryValue | string | Category of the activity log e.g. Administrative, Policy, Security. |
| Claims | string | The JWT token used by Active Directory to authenticate the user or application to perform this operation in Resource Manager. The use of claims_d should be preferred going forward. |
| Claims_d | dynamic | The JWT token used by Active Directory to authenticate the user or application to perform this operation in Resource Manager. |
| CorrelationId | string | Usually a GUID in the string format. Events that share a correlationId belong to the same uber action. |
| EventDataId | string | Unique identifier of an event. |
| EventSubmissionTimestamp | datetime | Timestamp when the event became available for querying. |
| Hierarchy | string | Management group hierarchy of the management group or subscription that event belongs to. |
| HTTPRequest | string | Blob describing the Http Request. Usually includes the “clientRequestId”, “clientIpAddress” and “method” (HTTP method. For example, PUT). |
| Level | string | Level of the event. One of the following values: Critical, Error, Warning, Informational and Verbose. |
| OperationId | string | GUID of the operation |
| OperationName | string |  |
| OperationNameValue | string | Identifier of the operation e.g. Microsoft.Storage/storageAccounts/listAccountSas/action. |
| Properties | string | Set of <Key Value> pairs (i.e. Dictionary) describing the details of the event. Stored as string. Usage of Properties_d is recommended instead. |
| Properties_d | dynamic | Set of <Key Value> pairs (i.e. Dictionary) describing the details of the event. Stored as dynamic column. |
| Resource | string |  |
| ResourceGroup | string | Resource group name of the impacted resource. |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceId | string |  |
| ResourceProvider | string |  |
| ResourceProviderValue | string | Id of the resource provider for the impacted resource - e.g. Microsoft.Storage. |
| SourceSystem | string | Azure is used always for AzureActivity |
| SubscriptionId | string | Subscription ID of the impacted resource. |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | ID of the worksapce that stores this record |
| TimeGenerated | datetime | Timestamp when the event was generated by the Azure service processing the request corresponding the event. |
| Type | string | The name of the table |
