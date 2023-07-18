---
title: Supported metrics - Microsoft.Cloudtest/hostedpools
description: Reference for Microsoft.Cloudtest/hostedpools metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Cloudtest/hostedpools  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Cloudtest/hostedpools resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Allocated<p><p>Resources that are allocated |`Allocated` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|
|AllocationDurationMs<p><p>Average time to allocate requests (ms) |`AllocationDurationMs` |Milliseconds |Average |PoolId, Type, ResourceRequestType, Image |Yes|
|Count<p><p>Number of requests in last dump |`Count` |Count |Count |RequestType, Status, PoolId, Type, ErrorCode, FailureStage |Yes|
|NotReady<p><p>Resources that are not ready to be used |`NotReady` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|
|PendingReimage<p><p>Resources that are pending reimage |`PendingReimage` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|
|PendingReturn<p><p>Resources that are pending return |`PendingReturn` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|
|Provisioned<p><p>Resources that are provisioned |`Provisioned` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|
|Ready<p><p>Resources that are ready to be used |`Ready` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|
|Starting<p><p>Resources that are starting |`Starting` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|
|Total<p><p>Total Number of Resources |`Total` |Count |Average |PoolId, SKU, Images, ProviderName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->