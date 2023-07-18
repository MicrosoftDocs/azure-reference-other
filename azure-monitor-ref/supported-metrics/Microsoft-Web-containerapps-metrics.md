---
title: Supported metrics - Microsoft.Web/containerapps
description: Reference for Microsoft.Web/containerapps metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Web/containerapps  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Web/containerapps resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Replica Count<p><p>Number of replicas count of container app |`Replicas` |Count |Maximum |revisionName, deploymentName |Yes|
|Requests<p><p>Requests processed |`Requests` |Count |Total |revisionName, podName, statusCodeCategory, statusCode |Yes|
|Replica Restart Count<p><p>Restart count of container app replicas |`RestartCount` |Count |Maximum |revisionName, podName |Yes|
|Network In Bytes<p><p>Network received bytes |`RxBytes` |Bytes |Total |revisionName, podName |Yes|
|Network Out Bytes<p><p>Network transmitted bytes |`TxBytes` |Bytes |Total |revisionName, podName |Yes|
|CPU Usage Nanocores<p><p>CPU consumed by the container app, in nano cores. 1,000,000,000 nano cores = 1 core |`UsageNanoCores` |NanoCores |Average |revisionName, podName |Yes|
|Memory Working Set Bytes<p><p>Container App working set memory used in bytes. |`WorkingSetBytes` |Bytes |Average |revisionName, podName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->