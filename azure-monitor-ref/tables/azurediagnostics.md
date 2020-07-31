---
title: Azure Monitor Logs reference - AzureDiagnostics
description: Reference for AzureDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: bwren
author: bwren
ms.date: 07/31/2020
---

# AzureDiagnostics

Stores resource logs for Azure services that use Azure Diagnostics mode. Resource logs describe the internal operation of Azure resources. All resource logs share a common top-level schema, which services extend to create unique properties for their specific events.

Azure services that use resource-specific mode store data in a table specific to that service and do not use the AzureDiagnostics table. See [Azure resource logs](https://docs.microsoft.com/azure/azure-monitor/platform/resource-logs#send-to-log-analytics-workspace) for details.


## Categories

- Azure Resources
- Security
- Network

## Solutions

- LogManagement

## Resource types

### Azure Diagnostics mode

- Analysis Services
- Application Gateways
- Automation Accounts
- Azure Database for MariaDB servers
- Azure Database for MySQL servers
- Azure Database for PostgreSQL servers
- Azure Database for PostgreSQL servers v2
- Batch accounts
- CDN profiles
- Cognitive Services
- Cosmos DB
- Data Lake Analytics
- DataLake Storage Gen1
- Device Provisioning Services
- Digital Twins
- Event Grid Topics
- Event Hubs
- ExpressRoute circuits
- Firewalls
- Front Doors
- Integration accounts
- Key Vault
- Load balancers
- Logic Apps
- Media services
- Network interfaces
- Network Security Groups
- P2S VPN Gateways
- Power BI Embedded
- Public IP addresses
- Recovery Services vaults(Site Recovery)
- Search services
- Service Bus
- SQL databases
- SQL managed Instances
- SQL servers
- Stream Analytics jobs
- Traffic Manager profiles
- Virtual networks
- Virtual network gateways
- VPN Gateways

### Azure Diagnostics mode or resource-specific mode

- API Management Services
- Data factories (V2)
- IoT Hub
- Kubernetes services
- Recovery Services vaults(Backup)


## Columns

|Column|Type|Description|
|---|---|---|
|Category|string||
|CorrelationId|string||
|OperationName|string||
|Resource|string||
|ResourceGroup|string||
|_ResourceId|string|A unique identifier for the resource that the record is associated with|
|ResourceId|string||
|ResourceProvider|string||
|ResourceType|string||
|ResultDescription|string||
|ResultType|string||
|SourceSystem|string||
|SubscriptionId|string||
|TenantId|string||
|TimeGenerated|datetime||
|Type|string|The name of the table|
