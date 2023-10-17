---
ms.service: azure-monitor
ms.topic: include
ms.date: 10/02/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Web/staticsites, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Data Out<p><p>BytesSent |`BytesSent` |Bytes |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|CdnPercentageOf4XX<p><p>CdnPercentageOf4XX |`CdnPercentageOf4XX` |Percent |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|CdnPercentageOf5XX<p><p>CdnPercentageOf5XX |`CdnPercentageOf5XX` |Percent |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|CdnRequestCount<p><p>CdnRequestCount |`CdnRequestCount` |Count |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|CdnResponseSize<p><p>CdnResponseSize |`CdnResponseSize` |Bytes |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|CdnTotalLatency<p><p>CdnTotalLatency |`CdnTotalLatency` |MilliSeconds |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|FunctionErrors<p><p>FunctionErrors |`FunctionErrors` |Count |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|FunctionHits<p><p>FunctionHits |`FunctionHits` |Count |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|SiteErrors<p><p>SiteErrors |`SiteErrors` |Count |Total |No Dimensions|PT5M, PT1H, P1D |Yes|
|SiteHits<p><p>SiteHits |`SiteHits` |Count |Total |No Dimensions|PT5M, PT1H, P1D |Yes|