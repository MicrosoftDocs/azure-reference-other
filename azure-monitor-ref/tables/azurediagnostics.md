---
title: Azure Monitor Logs reference - AzureDiagnostics
description: Reference for AzureDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: robb
author: rboucher
ms.date: 3/16/2020
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

- Analysis Services
- Azure Database for PostgreSQL server
- Azure Database for MariaDB server
- Device Provisioning Services
- Event Hub
- Application Gateway
- Firewall
- ExpressRoute circuit
- Azure Database for PostgreSQL server
- Front Door
- Network interface
- Network security group
- Public IP addresse
- Traffic Manager profile
- Virtual network gateway
- Virtual network
- Search Services
- Load balancer
- Azure Database for MySQL server
- SQL database
- SQL server
- Batch account
- CDN profile
- Media Services
- Azure Cache for Redis
- Cognitive Services
- Key vault
- IoT Hub
- Azure Cosmos DB account
- Logic App
- API Management services
- Automation account
- Data factory (V2)
- Recovery Services vault
- Data Lake Storage Gen1
- Data Lake Analytics
- Power BI Dedicated
- SQL Managed instance
- Stream Analytics
- Service Bus




## Columns

|Column|Type|Description|
|---|---|---|
|TenantId|string||
|TimeGenerated|datetime||
|ResourceId|string||
|Category|string||
|ResourceGroup|string||
|SubscriptionId|string||
|ResourceProvider|string||
|Resource|string||
|ResourceType|string||
|OperationName|string||
|ResultType|string||
|CorrelationId|string||
|ResultDescription|string||
|SourceSystem|string||
|ManagementGroupName|string||
|Computer|string||
|RawData|string||
|Type|string||
|_ResourceId|string||
