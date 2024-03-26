---
ms.service: azure-monitor
ms.topic: include
ms.date: 03/26/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Tables for microsoft.media/mediaservices
---


| Table | Categories | Solutions|[Supports basic log plan](/azure/azure-monitor/logs/basic-logs-configure?tabs=portal-1#compare-the-basic-and-analytics-log-data-plans)| Queries|
|---|---|---|---|---|
| [AMSKeyDeliveryRequests](/azure/azure-monitor/reference/tables/AMSKeyDeliveryRequests)<p>Key delivery requests logs from Azure Media Services. This table captures details for every HTTP request for key or license acquisition sent to Azure Media Services. It can be used to monitor encrypted content playback, and to diagnose issues with DRM license acquisition or Clear Key acquisition. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/amskeydeliveryrequests)|
| [AMSLiveEventOperations](/azure/azure-monitor/reference/tables/AMSLiveEventOperations)<p>Contains logs related to a Live Event. Logs are sent when an encoder connects, disconnects, or if there is a discontinuity in the media data. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/amsliveeventoperations)|
| [AMSMediaAccountHealth](/azure/azure-monitor/reference/tables/AMSMediaAccountHealth)<p>Media Account Health Status. This table captures the Azure Media Services account health status. It can be used to monitor account health status and diagnose issues for unhealthy accounts. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/amsmediaaccounthealth)|
| [AMSStreamingEndpointRequests](/azure/azure-monitor/reference/tables/AMSStreamingEndpointRequests)<p>Contains information about requests to streaming endpoints. A streaming endpoint receives HTTP requests needed to stream video content. These requests usually come from video players or from the CDN. | audit, resources | LogManagement | Yes| [Yes](/azure/azure-monitor/reference/queries/amsstreamingendpointrequests)|
| [AzureActivity](/azure/azure-monitor/reference/tables/AzureActivity)<p>Entries from the Azure Activity log that provides insight into any subscription-level or management group level events that have occurred in Azure. | resources, audit, security | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azureactivity)|
| [AzureMetrics](/azure/azure-monitor/reference/tables/AzureMetrics)<p>Metric data emitted by Azure services that measure their health and performance. | resources | LogManagement | No| [Yes](/azure/azure-monitor/reference/queries/azuremetrics)|

  
