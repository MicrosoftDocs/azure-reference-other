---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.CustomProviders/resourceproviders, arm
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Failed Requests<p><p>Gets the available logs for Custom Resource Providers |`FailedRequests` |Count |Total |HttpMethod, CallPath, StatusCode|PT15M, PT1H, PT12H, P1D |Yes|
|Successful Requests<p><p>Successful requests made by the custom provider |`SuccessfullRequests` |Count |Total |HttpMethod, CallPath, StatusCode|PT15M, PT1H, PT12H, P1D |Yes|