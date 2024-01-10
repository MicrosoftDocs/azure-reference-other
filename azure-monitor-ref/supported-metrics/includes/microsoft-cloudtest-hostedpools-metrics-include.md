---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Cloudtest/hostedpools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Saturation|**Allocated**<p><p>Resources that are allocated |`Allocated` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|
|Latency|**AllocationDurationMs**<p><p>Average time to allocate requests (ms) |`AllocationDurationMs` |Milliseconds |Average |`PoolId`, `Type`, `ResourceRequestType`, `Image`|PT1M |Yes|
|Traffic|**Count**<p><p>Number of requests in last dump |`Count` |Count |Count |`RequestType`, `Status`, `PoolId`, `Type`, `ErrorCode`, `FailureStage`|PT1M |Yes|
|Saturation|**NotReady**<p><p>Resources that are not ready to be used |`NotReady` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|
|Saturation|**PendingReimage**<p><p>Resources that are pending reimage |`PendingReimage` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|
|Saturation|**PendingReturn**<p><p>Resources that are pending return |`PendingReturn` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|
|Saturation|**Provisioned**<p><p>Resources that are provisioned |`Provisioned` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|
|Saturation|**Ready**<p><p>Resources that are ready to be used |`Ready` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|
|Saturation|**Starting**<p><p>Resources that are starting |`Starting` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|
|Saturation|**Total**<p><p>Total Number of Resources |`Total` |Count |Average, Maximum, Minimum |`PoolId`, `SKU`, `Images`, `ProviderName`|PT1M |Yes|