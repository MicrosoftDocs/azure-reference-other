---
title: Azure Monitor Logs reference - AzureDiagnostics
description: Reference for AzureDiagnostics table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/09/2023
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

- Application Gateways
- CDN Profiles
- Azure Cosmos DB
- Event Grid Topics
- Event Hubs
- Firewalls
- Key Vaults
- Kubernetes Services
- Recovery Services Vaults
- Service Bus
- Azure Database for MySQL Flexible Servers
- Azure Database for PostgreSQL Flexible Servers
- Media Services
- Analysis Services
- Batch Accounts
- Cognitive Services
- Event Grid Partner Namespaces
- Event Grid Partner Topics
- Event Grid System Topics
- Azure Arc Enabled Kubernetes
- Azure Arc Provisioned Clusters
- IoT Hub
- Logic Apps
- API Management services
- Automation account
- Data factories
- Data Lake Storage Gen1
- Data Lake Analytics
- Power BI Embedded
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




## Columns

| Column | Type | Description |
|---|---|---|
| _BilledSize | real | The record size in bytes |
| Category | string |   |
| CorrelationId | string |   |
| _IsBillable | string | Specifies whether ingesting the data is billable. When _IsBillable is `false` ingestion isn't billed to your Azure account |
| OperationName | string |   |
| Resource | string |   |
| ResourceGroup | string |   |
| ResourceId | string |   |
| _ResourceId | string | A unique identifier for the resource that the record is associated with |
| ResourceProvider | string |   |
| ResourceType | string |   |
| ResultDescription | string |   |
| ResultType | string |   |
| SourceSystem | string | The type of agent the event was collected by. For example, `OpsManager` for Windows agent, either direct connect or Operations Manager, `Linux` for all Linux agents, or `Azure` for Azure Diagnostics |
| SubscriptionId | string |   |
| _SubscriptionId | string | A unique identifier for the subscription that the record is associated with |
| TenantId | string | The Log Analytics workspace ID |
| TimeGenerated | datetime |   |
| Type | string | The name of the table |
