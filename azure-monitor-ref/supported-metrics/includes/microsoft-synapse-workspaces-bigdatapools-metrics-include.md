---
ms.service: azure-monitor
ms.topic: include
ms.date: 02/19/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Synapse/workspaces/bigDataPools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---


|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Apache Spark pool|**vCores allocated**<br><br>Allocated vCores for an Apache Spark Pool |`BigDataPoolAllocatedCores` |Count |Maximum, Minimum, Average, Total |`SubmitterId`|PT1M |No|
|Apache Spark pool|**Memory allocated (GB)**<br><br>Allocated Memory for Apach Spark Pool (GB) |`BigDataPoolAllocatedMemory` |Count |Maximum, Minimum, Average, Total |`SubmitterId`|PT1M |No|
|Apache Spark pool|**Active Apache Spark applications**<br><br>Total Active Apache Spark Pool Applications |`BigDataPoolApplicationsActive` |Count |Maximum, Minimum, Average |`JobState`|PT1M |No|
|Apache Spark pool|**Ended Apache Spark applications**<br><br>Count of Apache Spark pool applications ended |`BigDataPoolApplicationsEnded` |Count |Total |`JobType`, `JobResult`|PT1M |No|