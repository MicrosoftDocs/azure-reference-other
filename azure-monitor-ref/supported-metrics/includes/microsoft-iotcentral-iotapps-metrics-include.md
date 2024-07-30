---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.IoTCentral/IoTApps, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Failed command invocations**<br><br>The count of all failed command requests initiated from IoT Central |`c2d.commands.failure` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Request size of command invocations**<br><br>Request size of all command requests initiated from IoT Central |`c2d.commands.requestSize` |Bytes |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Response size of command invocations**<br><br>Response size of all command responses initiated from IoT Central |`c2d.commands.responseSize` |Bytes |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Successful command invocations**<br><br>The count of all successful command requests initiated from IoT Central |`c2d.commands.success` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Failed Device Property Reads from IoT Central**<br><br>The count of all failed property reads initiated from IoT Central |`c2d.property.read.failure` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Successful Device Property Reads from IoT Central**<br><br>The count of all successful property reads initiated from IoT Central |`c2d.property.read.success` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Failed Device Property Updates from IoT Central**<br><br>The count of all failed property updates initiated from IoT Central |`c2d.property.update.failure` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Successful Device Property Updates from IoT Central**<br><br>The count of all successful property updates initiated from IoT Central |`c2d.property.update.success` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Connected Devices**<br><br>Number of devices connected to IoT Central |`connectedDeviceCount` |Count |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|**Failed Device Property Reads from Devices**<br><br>The count of all failed property reads initiated from devices |`d2c.property.read.failure` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Successful Device Property Reads from Devices**<br><br>The count of all successful property reads initiated from devices |`d2c.property.read.success` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Failed Device Property Updates from Devices**<br><br>The count of all failed property updates initiated from devices |`d2c.property.update.failure` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Successful Device Property Updates from Devices**<br><br>The count of all successful property updates initiated from devices |`d2c.property.update.success` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Telemetry Message Send Attempts**<br><br>Number of device-to-cloud telemetry messages attempted to be sent to the IoT Central application |`d2c.telemetry.ingress.allProtocol` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Telemetry Messages Sent**<br><br>Number of device-to-cloud telemetry messages successfully sent to the IoT Central application |`d2c.telemetry.ingress.success` |Count |Total |\<none\>|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Data Export Errors**<br><br>Number of errors encountered for data export |`dataExport.error` |Count |Total |`exportId`, `exportDisplayName`, `destinationId`, `destinationDisplayName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Data Export Messages Filtered**<br><br>Number of messages that have passed through filters in data export |`dataExport.messages.filtered` |Count |Total |`exportId`, `exportDisplayName`, `destinationId`, `destinationDisplayName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Data Export Messages Received**<br><br>Number of messages incoming to data export, before filtering and enrichment processing |`dataExport.messages.received` |Count |Total |`exportId`, `exportDisplayName`, `destinationId`, `destinationDisplayName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Data Export Messages Written**<br><br>Number of messages written to a destination |`dataExport.messages.written` |Count |Total |`exportId`, `exportDisplayName`, `destinationId`, `destinationDisplayName`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Data Export Status Change**<br><br>Number of status changes |`dataExport.statusChange` |Count |Total |`exportId`, `exportDisplayName`, `destinationId`, `destinationDisplayName`, `status`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Device Data Usage**<br><br>Bytes transferred to and from any devices connected to IoT Central application |`deviceDataUsage` |Bytes |Total |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |Yes|
|**Total Provisioned Devices**<br><br>Number of devices provisioned in IoT Central application |`provisionedDeviceCount` |Count |Average |\<none\>|PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|