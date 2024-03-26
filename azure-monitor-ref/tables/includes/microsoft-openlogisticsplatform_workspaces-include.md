---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.openlogisticsplatform/workspaces
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [OLPSupplyChainEntityOperations](/azure/azure-monitor/reference/tables/OLPSupplyChainEntityOperations)<p>The OLPSupplyChainEntityOperations table captures every data plane operation performed on a supplychain entity in the workspace. Data Plane requests are operations executed to create, update, delete or retrieve supplychain entities such as Warehouse, Item, DeliveryNode, Shipment etc. within a workspace. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/olpsupplychainentityoperations)|
| [OLPSupplyChainEvents](/azure/azure-monitor/reference/tables/OLPSupplyChainEvents)<p>The events table captures every event that was dispatched from the Open Logistics Platform workspace. Events can be a result of a data plane API call (e.g. Shipment Created, Item Deleted, Notification sent, etc.) or a long running job operation completion (e.g. Data ingestion results in NewDataAvailable event). | resources | LogManagement | No| -|

  
