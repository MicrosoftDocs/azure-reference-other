---
title: Supported metrics - Microsoft.HealthModel/healthmodels
description: Reference for Microsoft.HealthModel/healthmodels metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 08/01/2023
---
# Supported metrics for Microsoft.HealthModel/healthmodels  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.HealthModel/healthmodels resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Query execution duration<p><p>Overall duration of executing all configured queries in parallel and calculating the model health state. |`ExecutionDuration` |Milliseconds |Average |No Dimensions |Yes|
|Health score per node<p><p>Health score per node in the model. Dimension splitting should be applied. Can be a value between 0 and 100 percent. Update frequency depends on the refreshInterval of the health model. Does not include the root node. |`NodeHealthScore` |Percent |Minimum |NodeName |Yes|
|Overall health score<p><p>The health score of the root node represents the overall health of the model. Can be a value between 0 and 100 percent. Update frequency depends on the refreshInterval of the health model. |`OverallHealthScore` |Percent |Minimum |No Dimensions |Yes|


<!--Gen Date:  Tue Aug 01 2023 10:39:24 GMT+0300 (Israel Daylight Time)-->