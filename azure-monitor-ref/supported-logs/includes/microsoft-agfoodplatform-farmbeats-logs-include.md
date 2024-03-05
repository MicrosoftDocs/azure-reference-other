---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/05/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.AgFoodPlatform/farmBeats, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`ApplicationAuditLogs` |Application Audit Logs |[AgriFoodApplicationAuditLogs](/azure/azure-monitor/reference/tables/agrifoodapplicationauditlogs)<p>Logs for privileged actions such as data-plane resource create, update, delete and subscription management operations.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/agrifoodapplicationauditlogs)|Yes |
|`FarmManagementLogs` |Farm Management Logs |[AgriFoodFarmManagementLogs](/azure/azure-monitor/reference/tables/agrifoodfarmmanagementlogs)<p>Logs for create, update, delete and get operations on FarmBeats resources such as Farmer, Farm, Field, Boundary, Seasonal Field, Crop, CropVariety, Season, Attachment, Prescription Maps, Prescriptions, Management Zones, Zones, Plant Tissue Analysis, Nutrient Analysis etc.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/agrifoodfarmmanagementlogs)|Yes |
|`FarmOperationLogs` |Farm Operation Logs |[AgriFoodFarmOperationLogs](/azure/azure-monitor/reference/tables/agrifoodfarmoperationlogs)<p>Logs for create, update, delete and get operations for FarmOperations such as data ingestion job, ApplicationData, PlantingData, HarvestingData, TillageData etc.|No|Yes||Yes |
|`InsightLogs` |Insight Logs |[AgriFoodInsightLogs](/azure/azure-monitor/reference/tables/agrifoodinsightlogs)<p>Logs for read operations on FarmBeats resources such as inisghts and inisight-attachments.|No|Yes||Yes |
|`JobProcessedLogs` |Job Processed Logs |[AgriFoodJobProcessedLogs](/azure/azure-monitor/reference/tables/agrifoodjobprocessedlogs)<p>Logs indicating success or failure of job runs for farmOperationDataIngestionJob, farmOperationPeriodicJob, farmOperationEventHandlingJob, satelliteDataIngestionJob, weatherDataIngestionJob etc. These logs also contain reasons for failure of these jobs if any.|No|Yes|[Queries](/azure/azure-monitor/reference/queries/agrifoodjobprocessedlogs)|Yes |
|`ModelInferenceLogs` |Model Inference Logs ||No|Yes||Yes |
|`ProviderAuthLogs` |Provider Auth Logs |[AgriFoodProviderAuthLogs](/azure/azure-monitor/reference/tables/agrifoodproviderauthlogs)<p>Logs for create, update, delete, cascade delete get and get all for oauth providers. It also has logs for get, get all and cascade delete for oauth tokens.|No|Yes||Yes |
|`SatelliteLogs` |Satellite Logs |[AgriFoodSatelliteLogs](/azure/azure-monitor/reference/tables/agrifoodsatellitelogs)<p>Logs for create and get operations for Satellite data.|No|Yes||Yes |
|`SensorManagementLogs` |Sensor Management Logs |[AgriFoodSensorManagementLogs](/azure/azure-monitor/reference/tables/agrifoodsensormanagementlogs)<p>Logs for sensors, sensors mappings, sensors events, sensors data models, sensors partner integration, devices, device data models etc.|No|No||Yes |
|`WeatherLogs` |Weather Logs |[AgriFoodWeatherLogs](/azure/azure-monitor/reference/tables/agrifoodweatherlogs)<p>Logs for create, update, delete and get operations while ingesting weather data in FarmBeats.|No|Yes||Yes |