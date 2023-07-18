---
title: Supported metrics - Microsoft.IoTCentral/IoTApps
description: Reference for Microsoft.IoTCentral/IoTApps metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.IoTCentral/IoTApps  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.IoTCentral/IoTApps resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Failed command invocations<p><p>The count of all failed command requests initiated from IoT Central |`c2d.commands.failure` |Count |Total |No Dimensions |Yes|
|Request size of command invocations<p><p>Request size of all command requests initiated from IoT Central |`c2d.commands.requestSize` |Bytes |Total |No Dimensions |Yes|
|Response size of command invocations<p><p>Response size of all command responses initiated from IoT Central |`c2d.commands.responseSize` |Bytes |Total |No Dimensions |Yes|
|Successful command invocations<p><p>The count of all successful command requests initiated from IoT Central |`c2d.commands.success` |Count |Total |No Dimensions |Yes|
|Failed Device Property Reads from IoT Central<p><p>The count of all failed property reads initiated from IoT Central |`c2d.property.read.failure` |Count |Total |No Dimensions |Yes|
|Successful Device Property Reads from IoT Central<p><p>The count of all successful property reads initiated from IoT Central |`c2d.property.read.success` |Count |Total |No Dimensions |Yes|
|Failed Device Property Updates from IoT Central<p><p>The count of all failed property updates initiated from IoT Central |`c2d.property.update.failure` |Count |Total |No Dimensions |Yes|
|Successful Device Property Updates from IoT Central<p><p>The count of all successful property updates initiated from IoT Central |`c2d.property.update.success` |Count |Total |No Dimensions |Yes|
|Total Connected Devices<p><p>Number of devices connected to IoT Central |`connectedDeviceCount` |Count |Average |No Dimensions |No|
|Failed Device Property Reads from Devices<p><p>The count of all failed property reads initiated from devices |`d2c.property.read.failure` |Count |Total |No Dimensions |Yes|
|Successful Device Property Reads from Devices<p><p>The count of all successful property reads initiated from devices |`d2c.property.read.success` |Count |Total |No Dimensions |Yes|
|Failed Device Property Updates from Devices<p><p>The count of all failed property updates initiated from devices |`d2c.property.update.failure` |Count |Total |No Dimensions |Yes|
|Successful Device Property Updates from Devices<p><p>The count of all successful property updates initiated from devices |`d2c.property.update.success` |Count |Total |No Dimensions |Yes|
|Total Telemetry Message Send Attempts<p><p>Number of device-to-cloud telemetry messages attempted to be sent to the IoT Central application |`d2c.telemetry.ingress.allProtocol` |Count |Total |No Dimensions |Yes|
|Total Telemetry Messages Sent<p><p>Number of device-to-cloud telemetry messages successfully sent to the IoT Central application |`d2c.telemetry.ingress.success` |Count |Total |No Dimensions |Yes|
|Data Export Errors<p><p>Number of errors encountered for data export |`dataExport.error` |Count |Total |exportId, exportDisplayName, destinationId, destinationDisplayName |Yes|
|Data Export Messages Filtered<p><p>Number of messages that have passed through filters in data export |`dataExport.messages.filtered` |Count |Total |exportId, exportDisplayName, destinationId, destinationDisplayName |Yes|
|Data Export Messages Received<p><p>Number of messages incoming to data export, before filtering and enrichment processing |`dataExport.messages.received` |Count |Total |exportId, exportDisplayName, destinationId, destinationDisplayName |Yes|
|Data Export Messages Written<p><p>Number of messages written to a destination |`dataExport.messages.written` |Count |Total |exportId, exportDisplayName, destinationId, destinationDisplayName |Yes|
|Data Export Status Change<p><p>Number of status changes |`dataExport.statusChange` |Count |Total |exportId, exportDisplayName, destinationId, destinationDisplayName, status |Yes|
|Total Device Data Usage<p><p>Bytes transferred to and from any devices connected to IoT Central application |`deviceDataUsage` |Bytes |Total |No Dimensions |Yes|
|Total Provisioned Devices<p><p>Number of devices provisioned in IoT Central application |`provisionedDeviceCount` |Count |Average |No Dimensions |No|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->