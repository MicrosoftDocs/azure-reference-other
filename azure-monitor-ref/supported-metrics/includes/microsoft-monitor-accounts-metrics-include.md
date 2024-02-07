---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/07/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Monitor/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Active Time Series**<p><p> The number of unique time series recently ingested into the account over the previous 12 hours |`ActiveTimeSeries` |Count |Maximum |`StampColor`|PT1M |No|
|**Active Time Series Limit**<p><p>The limit on the number of unique time series which can be actively ingested into the account |`ActiveTimeSeriesLimit` |Count |Average, Maximum |`StampColor`|PT1M |No|
|**Active Time Series % Utilization**<p><p>The percentage of current active time series account limit being utilized |`ActiveTimeSeriesPercentUtilization` |Percent |Average |`StampColor`|PT1M |No|
|**Events Per Minute Ingested**<p><p>The number of events per minute recently received |`EventsPerMinuteIngested` |Count |Maximum |`StampColor`|PT1M |No|
|**Events Per Minute Ingested Limit**<p><p>The maximum number of events per minute which can be received before events become throttled |`EventsPerMinuteIngestedLimit` |Count |Average, Maximum |`StampColor`|PT1M |No|
|**Events Per Minute Ingested % Utilization**<p><p>The percentage of the current metric ingestion rate limit being utilized |`EventsPerMinuteIngestedPercentUtilization` |Percent |Average |`StampColor`|PT1M |No|