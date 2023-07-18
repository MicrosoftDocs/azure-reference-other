---
title: Supported metrics - Microsoft.Media/videoanalyzers
description: Reference for Microsoft.Media/videoanalyzers metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Media/videoanalyzers  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Media/videoanalyzers resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Ingress Bytes<p><p>The number of bytes ingressed by the pipeline node. |`IngressBytes` |Bytes |Total |PipelineKind, PipelineTopology, Pipeline, Node |Yes|
|Pipelines<p><p>The number of pipelines of each kind and state |`Pipelines` |Count |Total |PipelineKind, PipelineTopology, PipelineState |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->