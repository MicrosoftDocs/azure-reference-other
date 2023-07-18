---
title: Supported metrics - Microsoft.Devices/provisioningServices
description: Reference for Microsoft.Devices/provisioningServices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Devices/provisioningServices  
<!-- Data source : arm-->


The following table lists the metrics available for the Microsoft.Devices/provisioningServices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Attestation attempts<p><p>Number of device attestations attempted |`AttestationAttempts` |Count |Total |ProvisioningServiceName, Status, Protocol |Yes|
|Devices assigned<p><p>Number of devices assigned to an IoT hub |`DeviceAssignments` |Count |Total |ProvisioningServiceName, IotHubName |Yes|
|Registration attempts<p><p>Number of device registrations attempted |`RegistrationAttempts` |Count |Total |ProvisioningServiceName, IotHubName, Status |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->