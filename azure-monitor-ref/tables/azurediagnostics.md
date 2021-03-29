---
title: Azure Monitor Logs reference - AzureDiagnostics
description: Reference for AzureDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 3/29/2021
---

# AzureDiagnostics

 Diagnostic logs emitted by Azure services describe the operation of those services or resources. All diagnostic logs share a common top-level schema, which services extend to emit unique properties for their specifc events. Note: many services are now ingesting their diagnostic logs into resource-specific tables, see more here

## Categories

- Azure Resources
- Security
- Network
## Solutions

- LogManagement
## Resource types

- Kubernetes Services
- Azure Database for PostgreSQL Servers
- Azure Database for PostgreSQL Servers V2
- Azure Database for PostgreSQL Flexible Servers
- Azure Database for MariaDB Servers
- Device Provisioning Services
- Event Hubs
- Application Gateways
- Firewalls
- Azure Database for MySQL Servers
- ExpressRoute Circuits
- Network Interfaces
- Network Security Groups
- Public IP Addresses
- Traffic Manager Profiles
- Virtual Network Gateways
- Virtual Private Network Gateways
- Virtual Networks
- Search Services
- Front Doors
- SQL Databases
- SQL Servers
- SQL Managed Instances
- Event Grid Topics
- Analysis Services
- Batch Accounts
- CDN Profiles
- Media Services
- Azure Cache for Redis
- Cognitive Services
- Key Vaults
- Azure Arc enabled Kubernetes
- IoT Hub
- Azure Cosmos DB
- Logic Apps
- API Management services
- Automation account
- Data factories
- Recovery Services Vaults
- Data Lake Storage Gen1
- Data Lake Analytics
- Power BI Embedded
- Stream Analytics jobs
- Service Bus




## Columns

|Column|Type|Description|
|---|---|---|
|Category|string||
|CorrelationId|string||
|OperationName|string||
|Resource|string||
|ResourceGroup|string||
|ResourceId|string||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceProvider|string||
|ResourceType|string||
|ResultDescription|string||
|ResultType|string||
|SourceSystem|string||
|_SubscriptionId|string|A unique identifier for the subscription that the record is associated with|
|SubscriptionId|string||
|TenantId|string||
|TimeGenerated|datetime||
|Type|string|The name of the table|
