---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/02/2024
ms.author: orens
author: osalzberg
ms.custom: Microsoft.EventGrid/namespaces, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---
  
  
|Category|Category display name| Log table| [Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)|[Supports ingestion-time transformation](/azure/azure-monitor/essentials/data-collection-transformations)| Example queries |Costs to export|
|---|---|---|---|---|---|---|
|`FailedHttpDataPlaneOperations` |Failed HTTP data plane operations logs ||No|No||Yes |
|`FailedMqttConnections` |Failed MQTT Connections |[EGNFailedMqttConnections](/azure/azure-monitor/reference/tables/egnfailedmqttconnections)<p>Log for failed MQTT connections to an Event Grid namespace.|No|No|[Queries](/azure/azure-monitor/reference/queries/egnfailedmqttconnections)|Yes |
|`FailedMqttPublishedMessages` |Failed MQTT Published Messages |[EGNFailedMqttPublishedMessages](/azure/azure-monitor/reference/tables/egnfailedmqttpublishedmessages)<p>Log for failed MQTT published messages to an Event Grid namespace.|No|No||Yes |
|`FailedMqttSubscriptionOperations` |Failed MQTT Subscription Operations ||No|No||Yes |
|`MqttDisconnections` |MQTT Disconnections |[EGNMqttDisconnections](/azure/azure-monitor/reference/tables/egnmqttdisconnections)<p>Log for disconnected MQTT connections from an Event Grid namespace.|No|No|[Queries](/azure/azure-monitor/reference/queries/egnmqttdisconnections)|Yes |
|`SuccessfulHttpDataPlaneOperations` |Successful HTTP data plane operations logs |[EGNSuccessfulHttpDataPlaneOperations](/azure/azure-monitor/reference/tables/egnsuccessfulhttpdataplaneoperations)<p>Log for successful HTTP data plane requests to an Event Grid namespace. It can be used for auditing purposes.|No|No|[Queries](/azure/azure-monitor/reference/queries/egnsuccessfulhttpdataplaneoperations)|Yes |
|`SuccessfulMqttConnections` |Successful MQTT Connections |[EGNSuccessfulMqttConnections](/azure/azure-monitor/reference/tables/egnsuccessfulmqttconnections)<p>Log for successful MQTT connections to an Event Grid namesapce. This log can be used for auditing purposes.|No|No|[Queries](/azure/azure-monitor/reference/queries/egnsuccessfulmqttconnections)|Yes |