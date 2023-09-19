---
ms.service: azure-monitor
ms.topic: include
ms.date: 09/19/2023
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataLakeAnalytics/accounts, naam
---
  
  
|Metric|Name|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|Cancelled AU Time<p><p>Total AU time for cancelled jobs. |`JobAUEndedCancelled` |Seconds |Total |No Dimensions|PT1M |Yes|
|Failed AU Time<p><p>Total AU time for failed jobs. |`JobAUEndedFailure` |Seconds |Total |No Dimensions|PT1M |Yes|
|Successful AU Time<p><p>Total AU time for successful jobs. |`JobAUEndedSuccess` |Seconds |Total |No Dimensions|PT1M |Yes|
|Cancelled Jobs<p><p>Count of cancelled jobs. |`JobEndedCancelled` |Count |Total |No Dimensions|PT1M |Yes|
|Failed Jobs<p><p>Count of failed jobs. |`JobEndedFailure` |Count |Total |No Dimensions|PT1M |Yes|
|Successful Jobs<p><p>Count of successful jobs. |`JobEndedSuccess` |Count |Total |No Dimensions|PT1M |Yes|
|Jobs in Stage<p><p>Number of jobs in each stage. |`JobStage` |Count |Total |No Dimensions|PT1M |Yes|