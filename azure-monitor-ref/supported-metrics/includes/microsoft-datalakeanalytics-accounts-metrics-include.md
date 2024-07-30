---
ms.service: azure-monitor
ms.topic: include
author: EdB-MSFT
ms.author: edbaynash
ms.date: 07/30/2024
ms.custom: Microsoft.DataLakeAnalytics/accounts, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|
|**Cancelled AU Time**<br><br>Total AU time for cancelled jobs. |`JobAUEndedCancelled` |Seconds |Total |\<none\>|PT1M |Yes|
|**Failed AU Time**<br><br>Total AU time for failed jobs. |`JobAUEndedFailure` |Seconds |Total |\<none\>|PT1M |Yes|
|**Successful AU Time**<br><br>Total AU time for successful jobs. |`JobAUEndedSuccess` |Seconds |Total |\<none\>|PT1M |Yes|
|**Cancelled Jobs**<br><br>Count of cancelled jobs. |`JobEndedCancelled` |Count |Total |\<none\>|PT1M |Yes|
|**Failed Jobs**<br><br>Count of failed jobs. |`JobEndedFailure` |Count |Total |\<none\>|PT1M |Yes|
|**Successful Jobs**<br><br>Count of successful jobs. |`JobEndedSuccess` |Count |Total |\<none\>|PT1M |Yes|
|**Jobs in Stage**<br><br>Number of jobs in each stage. |`JobStage` |Count |Total |\<none\>|PT1M |Yes|