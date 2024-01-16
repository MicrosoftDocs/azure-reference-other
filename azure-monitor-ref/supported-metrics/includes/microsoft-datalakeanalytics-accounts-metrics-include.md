---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.DataLakeAnalytics/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Cancelled AU Time**<p><p>Total AU time for cancelled jobs. |`JobAUEndedCancelled` |Seconds |Total |\<none\>|PT1M |Yes|
|**Failed AU Time**<p><p>Total AU time for failed jobs. |`JobAUEndedFailure` |Seconds |Total |\<none\>|PT1M |Yes|
|**Successful AU Time**<p><p>Total AU time for successful jobs. |`JobAUEndedSuccess` |Seconds |Total |\<none\>|PT1M |Yes|
|**Cancelled Jobs**<p><p>Count of cancelled jobs. |`JobEndedCancelled` |Count |Total |\<none\>|PT1M |Yes|
|**Failed Jobs**<p><p>Count of failed jobs. |`JobEndedFailure` |Count |Total |\<none\>|PT1M |Yes|
|**Successful Jobs**<p><p>Count of successful jobs. |`JobEndedSuccess` |Count |Total |\<none\>|PT1M |Yes|
|**Jobs in Stage**<p><p>Number of jobs in each stage. |`JobStage` |Count |Total |\<none\>|PT1M |Yes|