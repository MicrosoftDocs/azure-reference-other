---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/videoanalyzers, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Ingress Bytes<p><p>The number of bytes ingressed by the pipeline node. |`IngressBytes` |Bytes |Total |PipelineKind, PipelineTopology, Pipeline, Node|PT1M |Yes|
|Pipelines<p><p>The number of pipelines of each kind and state |`Pipelines` |Count |Total |PipelineKind, PipelineTopology, PipelineState|PT5M |Yes|