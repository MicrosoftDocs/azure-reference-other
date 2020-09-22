---
title: Azure Monitor Logs reference - AzureActivity
description: Reference for AzureActivity table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 9/17/2020
---

# AzureActivity

 Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure.

## Categories

- Security
- Audit
- Azure Resources
## Solutions

- LogManagement
## Resource types

- SQL Databases
- Azure Database for MySQL Servers
- SQL Managed Instances
- SQL Servers
- Azure Database for PostgreSQL Servers
- Azure Database for MariaDB Servers
- Device Provisioning Services
- Azure Database for PostgreSQL Servers V2
- Azure Database for PostgreSQL Flexible Servers
- Automation account
- Data factories
- Logic Apps
- API Management services
- Recovery Services Vaults
- Power BI Embedded
- Data Share
- Data Lake Storage Gen1
- Data Lake Analytics
- Virtual Private Network Gateways
- Virtual Networks
- Traffic Manager Profiles
- Virtual Network Gateways
- Search Services
- Azure API for FHIR
- Service Bus
- Stream Analytics jobs
- Bastions
- Firewalls
- ExpressRoute Circuits
- Event Hubs
- Application Gateways
- Front Doors
- Network Security Groups
- Public IP Addresses
- Load Balancers
- Network Interfaces
- Service Fabric Clusters
- Workload Monitor
- Analysis Services
- Time Series Insights Environments
- Event Grid Topics
- Batch Accounts
- Media Services
- Azure Cache for Redis
- CDN Profiles
- Azure Spring Cloud
- Default schema for a resource
- Azure Subscription
- Network Watcher - Connection Monitor
- HDInsight Clusters
- Azure Resource Group
- Desktop Virtualization Host Pools
- Desktop Virtualization workspaces
- Application Insights
- Desktop Virtualization Application Groups
- Virtual Machine Scale Sets
- Kubernetes Services
- Event Grid Domains
- Virtual machines
- Azure Databricks Services
- Azure Cosmos DB
- Machine Learning
- Azure Monitor autoscale settings
- IoT Hub
- App Services
- Storage Accounts
- Cognitive Services
- Key Vaults
- SignalR
- Azure AD Domain Services
- Azure Blockchain Service
- Container Registries
- Azure Data Explorer Clusters




## Columns

|Column|Type|Description|
|---|---|---|
|ActivityStatus|string||
|ActivityStatusValue|string|Status of the operation in display-friendly format. Common values include Started, In Progress, Succeeded, Failed, Active, Resolved.|
|ActivitySubstatus|string||
|ActivitySubstatusValue|string|Substatus of the operation  in display-friendly format. E.g. OK (HTTP Status Code: 200).|
|Authorization|string|Blob of RBAC properties of the event. Usually includes the “action”, “role” and “scope” properties. Stored as string. The use of Authorization_d should be preferred going forward.|
|Authorization_d|dynamic|Blob of RBAC properties of the event. Usually includes the “action”, “role” and “scope” properties. Stored as dynamic column.|
|Caller|string|GUID of the caller.|
|CallerIpAddress|string|IP address of the user who has performed the operation UPN claim or SPN claim based on availability.|
|Category|string||
|CategoryValue|string|Category of the activity log e.g. Administrative, Policy, Security.|
|Claims|string|The JWT token used by Active Directory to authenticate the user or application to perform this operation in Resource Manager. The use of claims_d should be preferred going forward.|
|Claims_d|dynamic|The JWT token used by Active Directory to authenticate the user or application to perform this operation in Resource Manager.|
|CorrelationId|string|Usually a GUID in the string format. Events that share a correlationId belong to the same uber action.|
|EventDataId|string|Unique identifier of an event.|
|EventSubmissionTimestamp|datetime|Timestamp when the event became available for querying.|
|Hierarchy|string|Management group hierarchy of the management group or subscription that event belongs to.|
|HTTPRequest|string|Blob describing the Http Request. Usually includes the “clientRequestId”, “clientIpAddress” and “method” (HTTP method. For example, PUT).|
|Level|string|Level of the event. One of the following values: Critical, Error, Warning, Informational and Verbose.|
|OperationId|string|GUID of the operation|
|OperationName|string||
|OperationNameValue|string|Identifier of the operation e.g. Microsoft.Storage/storageAccounts/listAccountSas/action.|
|Properties|string|Set of <Key Value> pairs (i.e. Dictionary) describing the details of the event. Stored as string. Usage of Properties_d is recommended instead.|
|Properties_d|dynamic|Set of <Key Value> pairs (i.e. Dictionary) describing the details of the event. Stored as dynamic column.|
|Resource|string||
|ResourceGroup|string|Resource group name of the impacted resource.|
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceId|string||
|ResourceProvider|string||
|ResourceProviderValue|string|Id of the resource provider for the impacted resource - e.g. Microsoft.Storage.|
|SourceSystem|string|Azure is used always for AzureActivity|
|SubscriptionId|string|Subscription ID of the impacted resource.|
|TenantId|string|ID of the worksapce that stores this record|
|TimeGenerated|datetime|Timestamp when the event was generated by the Azure service processing the request corresponding the event.|
|Type|string|The name of the table|
