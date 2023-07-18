---
title: Supported metrics - Microsoft.Media/mediaservices/liveEvents
description: Reference for Microsoft.Media/mediaservices/liveEvents metrics in Azure Monitor.
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/12/2023
---
# Supported metrics for Microsoft.Media/mediaservices/liveEvents  
<!-- Data source : naam-->


The following table lists the metrics available for the Microsoft.Media/mediaservices/liveEvents resource type.

  

**Table headings**
  
**Metric** - Metric display name follows by a description of the metric. The displayname appears in the Azure portal.  
**Name** - The name of the metric as referred to in the REST API.  
**Unit** - The default units used for the metric.  
**Aggregation** - The default aggregation type for this metric. Valid values: Average, Minimum, Maximum, Total, Count.  
**Dimensions** - Dimensions available. For more information, see (link to dimensions information).  
**DS Export**- Whether the metric is exportable to Azure Monitor Logs via Diagnostic Settings.  You can access all metrics via the REST API.  
  
  
|Metric|Name|Unit|Aggregation|Dimensions|DS Export|
|---|---|---|---|---|---|
|Live Event ingest bitrate<p><p>The incoming bitrate ingested for a live event, in bits per second. |`IngestBitrate` |BitsPerSecond |Average |TrackName |Yes|
|Live Event ingest drift value<p><p>Drift between the timestamp of the ingested content and the system clock, measured in seconds per minute. A non zero value indicates that the ingested content is arriving slower than system clock time. |`IngestDriftValue` |Seconds |Maximum |TrackName |Yes|
|Live Event ingest last timestamp<p><p>Last timestamp ingested for a live event. |`IngestLastTimestamp` |Milliseconds |Maximum |TrackName |Yes|
|Last output timestamp<p><p>Timestamp of the last fragment uploaded to storage for a live event output. |`LiveOutputLastTimestamp` |Milliseconds |Maximum |TrackName |Yes|


<!--Gen Date:  Wed Jul 12 2023 17:59:09 GMT+0300 (Israel Daylight Time)-->