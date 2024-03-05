---
title: Azure Monitor Logs reference - UCDeviceAlert
description: Reference for UCDeviceAlert table in Azure Monitor Logs.
ms.topic: reference
ms.service: azure-monitor
ms.subservice: logs
ms.author: edbaynash
author: EdB-MSFT
ms.date: 03/05/2024
---

# UCDeviceAlert

Update Compliance - These alerts are activated as a result of an issue that is device-specific, and is not specific to a specific update and a specific device. Like UpdateAlerts, the AlertType indicates where the Alert comes from (ServiceDeviceAlert, ClientDeviceAlert). For example, an EndOfService alert is a ClientDeviceAlert, as the fact it is on a build no longer being serviced (EOS) is a client-wide state. Meanwhile, DeviceRegistrationIssues in WUfB DS will be a ServiceDeviceAlert, as it is a device-wide state in the service to not be correctly registered.


## Table attributes

|Attribute|Value|
|---|---|
|**Resource types**|-|
|**Categories**|-|
|**Solutions**| LogManagement, WaaSUpdateInsights|
|**Basic log**|No|
|**Ingestion-time transformation**|Yes|
|**Sample Queries**|-|



## Columns
  
[!INCLUDE [ucdevicealert](.././tables/includes/ucdevicealert-include.md)]
