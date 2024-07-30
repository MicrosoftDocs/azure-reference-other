---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.Media/mediaservices/liveEvents, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Live Event ingest bitrate**<br><br>The incoming bitrate ingested for a live event, in bits per second. |`IngestBitrate` |BitsPerSecond |Average, Minimum, Maximum |`TrackName`|PT1M |Yes|
|**Live Event ingest drift value**<br><br>Drift between the timestamp of the ingested content and the system clock, measured in seconds per minute. A non zero value indicates that the ingested content is arriving slower than system clock time. |`IngestDriftValue` |Seconds |Maximum |`TrackName`|PT1M |Yes|
|**Live Event ingest last timestamp**<br><br>Last timestamp ingested for a live event. |`IngestLastTimestamp` |Milliseconds |Maximum |`TrackName`|PT1M |Yes|
|**Last output timestamp**<br><br>Timestamp of the last fragment uploaded to storage for a live event output. |`LiveOutputLastTimestamp` |Milliseconds |Maximum |`TrackName`|PT1M |Yes|