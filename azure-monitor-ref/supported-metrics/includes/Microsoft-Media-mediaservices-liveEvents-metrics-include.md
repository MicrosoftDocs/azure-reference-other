---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Media/mediaservices/liveEvents, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Live Event ingest bitrate<p><p>The incoming bitrate ingested for a live event, in bits per second. |`IngestBitrate` |BitsPerSecond |Average, Minimum, Maximum |TrackName|PT1M |Yes|
|Live Event ingest drift value<p><p>Drift between the timestamp of the ingested content and the system clock, measured in seconds per minute. A non zero value indicates that the ingested content is arriving slower than system clock time. |`IngestDriftValue` |Seconds |Maximum |TrackName|PT1M |Yes|
|Live Event ingest last timestamp<p><p>Last timestamp ingested for a live event. |`IngestLastTimestamp` |Milliseconds |Maximum |TrackName|PT1M |Yes|
|Last output timestamp<p><p>Timestamp of the last fragment uploaded to storage for a live event output. |`LiveOutputLastTimestamp` |Milliseconds |Maximum |TrackName|PT1M |Yes|