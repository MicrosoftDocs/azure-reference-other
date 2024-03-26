---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.agfoodplatform/farmbeats
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AgriFoodApplicationAuditLogs](/azure/azure-monitor/reference/tables/AgriFoodApplicationAuditLogs)<p>Logs for privileged actions such as data-plane resource create, update, delete and subscription management operations. | audit, resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/agrifoodapplicationauditlogs)|
| [AgriFoodFarmManagementLogs](/azure/azure-monitor/reference/tables/AgriFoodFarmManagementLogs)<p>Logs for create, update, delete and get operations on FarmBeats resources such as Farmer, Farm, Field, Boundary, Seasonal Field, Crop, CropVariety, Season, Attachment, Prescription Maps, Prescriptions, Management Zones, Zones, Plant Tissue Analysis, Nutrient Analysis etc. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/agrifoodfarmmanagementlogs)|
| [AgriFoodFarmOperationLogs](/azure/azure-monitor/reference/tables/AgriFoodFarmOperationLogs)<p>Logs for create, update, delete and get operations for FarmOperations such as data ingestion job, ApplicationData, PlantingData, HarvestingData, TillageData etc. | resources | LogManagement | No| -|
| [AgriFoodInsightLogs](/azure/azure-monitor/reference/tables/AgriFoodInsightLogs)<p>Logs for read operations on FarmBeats resources such as inisghts and inisight-attachments. | resources | LogManagement | No| -|
| [AgriFoodJobProcessedLogs](/azure/azure-monitor/reference/tables/AgriFoodJobProcessedLogs)<p>Logs indicating success or failure of job runs for farmOperationDataIngestionJob, farmOperationPeriodicJob, farmOperationEventHandlingJob,satelliteDataIngestionJob, weatherDataIngestionJob etc. These logs also contain reasons for failure of these jobs if any. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/agrifoodjobprocessedlogs)|
| [AgriFoodModelInferenceLogs](/azure/azure-monitor/reference/tables/AgriFoodModelInferenceLogs)<p>Logs for create and get operations for AI/ML model inference jobs. | resources | LogManagement | No| -|
| [AgriFoodProviderAuthLogs](/azure/azure-monitor/reference/tables/AgriFoodProviderAuthLogs)<p>Logs for create, update, delete, cascade delete get and get all for oauth providers. It also has logs for get, get all and cascade delete for oauth tokens. | resources | LogManagement | No| -|
| [AgriFoodSatelliteLogs](/azure/azure-monitor/reference/tables/AgriFoodSatelliteLogs)<p>Logs for create and get operations for Satellite data. | resources | LogManagement | No| -|
| [AgriFoodSensorManagementLogs](/azure/azure-monitor/reference/tables/AgriFoodSensorManagementLogs)<p>Logs for sensors, sensors mappings, sensors events, sensors data models, sensors partner integration, devices, device data models etc. | resources | LogManagement | No| -|
| [AgriFoodWeatherLogs](/azure/azure-monitor/reference/tables/AgriFoodWeatherLogs)<p>Logs for create, update, delete and get operations while ingesting weather data in FarmBeats. | resources | LogManagement | No| -|

  
