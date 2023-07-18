---
title: Supported metrics - microsoft.hybridnetwork/virtualnetworkfunctions
description: Reference for microsoft.hybridnetwork/virtualnetworkfunctions metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for microsoft.hybridnetwork/virtualnetworkfunctions  
<!-- Data source : naam-->


The following table lists the metrics available for the microsoft.hybridnetwork/virtualnetworkfunctions resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Average CPU Utilization<p><p>Total average percentage of virtual CPU utilization at one minute interval. The total number of virtual CPU is based on user configured value in SKU definition. Further filter can be applied based on RoleName defined in SKU. |`HyperVVirtualProcessorUtilization` |Percent |Average |InstanceName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->