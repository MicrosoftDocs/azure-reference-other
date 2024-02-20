---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/videoanalyzers, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Pipeline|**Ingress Bytes**<br><br>The number of bytes ingressed by the pipeline node. |`IngressBytes` |Bytes |Total |`PipelineKind`, `PipelineTopology`, `Pipeline`, `Node`|PT1M |Yes|
|Pipeline|**Pipelines**<br><br>The number of pipelines of each kind and state |`Pipelines` |Count |Total |`PipelineKind`, `PipelineTopology`, `PipelineState`|PT5M |Yes|