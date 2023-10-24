---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/18/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/videoanalyzers, naam
---
<!--
NOTE:  This content is automatically generated using API calls to Azure. 
Any edits made on these files will be overwritten in the next run of the script. 
There is no benefit in editing these files directly.  
-->
  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Ingress Bytes**<p><p>The number of bytes ingressed by the pipeline node. |`IngressBytes` |Bytes |Total |`PipelineKind`, `PipelineTopology`, `Pipeline`, `Node`|PT1M |Yes|
|**Pipelines**<p><p>The number of pipelines of each kind and state |`Pipelines` |Count |Total |`PipelineKind`, `PipelineTopology`, `PipelineState`|PT5M |Yes|