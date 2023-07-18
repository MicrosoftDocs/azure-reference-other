---
title: Supported metrics - Microsoft.Media/mediaservices
description: Reference for Microsoft.Media/mediaservices metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Media/mediaservices  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Media/mediaservices resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Asset count<p><p>How many assets are already created in current media service account |`AssetCount` |Count |Average |No Dimensions |Yes|
|Asset quota<p><p>How many assets are allowed for current media service account |`AssetQuota` |Count |Average |No Dimensions |Yes|
|Asset quota used percentage<p><p>Asset used percentage in current media service account |`AssetQuotaUsedPercentage` |Percent |Average |No Dimensions |Yes|
|Live event count<p><p>The total number of live events in the current media services account |`ChannelsAndLiveEventsCount` |Count |Average |No Dimensions |Yes|
|Content Key Policy count<p><p>How many content key policies are already created in current media service account |`ContentKeyPolicyCount` |Count |Average |No Dimensions |Yes|
|Content Key Policy quota<p><p>How many content key polices are allowed for current media service account |`ContentKeyPolicyQuota` |Count |Average |No Dimensions |Yes|
|Content Key Policy quota used percentage<p><p>Content Key Policy used percentage in current media service account |`ContentKeyPolicyQuotaUsedPercentage` |Percent |Average |No Dimensions |Yes|
|Job quota<p><p>The Job quota for the current media service account. |`JobQuota` |Count |Average |No Dimensions |Yes|
|Jobs Scheduled<p><p>The number of Jobs in the Scheduled state. Counts on this metric only reflect jobs submitted through the v3 API. Jobs submitted through the v2 (Legacy) API are not counted. |`JobsScheduled` |Count |Average |No Dimensions |Yes|
|Key request time<p><p>The key delivery request status and latency in milliseconds for the current Media Service account. |`KeyDeliveryRequests` |Count |Average |KeyType, HttpStatusCode |No|
|Max live event quota<p><p>The maximum number of live events allowed in the current media services account |`MaxChannelsAndLiveEventsCount` |Count |Average |No Dimensions |Yes|
|Max running live event quota<p><p>The maximum number of running live events allowed in the current media services account |`MaxRunningChannelsAndLiveEventsCount` |Count |Average |No Dimensions |Yes|
|Running live event count<p><p>The total number of running live events in the current media services account |`RunningChannelsAndLiveEventsCount` |Count |Average |No Dimensions |Yes|
|Streaming Policy count<p><p>How many streaming policies are already created in current media service account |`StreamingPolicyCount` |Count |Average |No Dimensions |Yes|
|Streaming Policy quota<p><p>How many streaming policies are allowed for current media service account |`StreamingPolicyQuota` |Count |Average |No Dimensions |Yes|
|Streaming Policy quota used percentage<p><p>Streaming Policy used percentage in current media service account |`StreamingPolicyQuotaUsedPercentage` |Percent |Average |No Dimensions |Yes|
|Transform quota<p><p>The Transform quota for the current media service account. |`TransformQuota` |Count |Average |No Dimensions |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->