---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.CustomProviders/resourceproviders, arm

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Failed Requests**<br><br>Gets the available logs for Custom Resource Providers |`FailedRequests` |Count |Total |`HttpMethod`, `CallPath`, `StatusCode`|PT15M, PT1H, PT12H, P1D |Yes|
|**Successful Requests**<br><br>Successful requests made by the custom provider |`SuccessfullRequests` |Count |Total |`HttpMethod`, `CallPath`, `StatusCode`|PT15M, PT1H, PT12H, P1D |Yes|