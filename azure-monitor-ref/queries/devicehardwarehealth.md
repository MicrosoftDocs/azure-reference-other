---
title: Example log table queries for DeviceHardwareHealth
description:  Example queries for DeviceHardwareHealth log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DeviceHardwareHealth table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Hardware Minor  


SurfaceHub hardware minor.  

```query
DeviceHardwareHealth 
|where EventName != "CameraInUnexpectedState" and EventName != "WiredIngestInUnexpectedState" and EventName != "WiredTouchInUnexpectedState" and EventName != "WifiDirectInUnexpectedState" and EventName != "MicInUnexpectedState" and EventName != "WiredTouchInUnexpectedState" and EventName != "SpeakersInUnexpectedState" and EventName != "WirelessCardInUnexpectedState" 
| sort by TimeGenerated des
```



### Hardware Alert  


SurfaceHubHardwareAlert.  

```query
DeviceHardwareHealth
|where EventName == "CameraInUnexpectedState" or EventName == "WiredIngestInUnexpectedState" or EventName == "WiredTouchInUnexpectedState" or EventName == "WifiDirectInUnexpectedState" or EventName == "MicInUnexpectedState" or EventName == "WiredTouchInUnexpectedState" or EventName == "SpeakersInUnexpectedState" or EventName == "WirelessCardInUnexpectedState" 
| sort by TimeGenerated desc
```

