---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.Synapse/workspaces/bigDataPools, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Apache Spark pool|**vCores allocated**<p><p>Allocated vCores for an Apache Spark Pool |`BigDataPoolAllocatedCores` |Count |Maximum, Minimum, Average, Total |`SubmitterId`|PT1M |No|
|Apache Spark pool|**Memory allocated (GB)**<p><p>Allocated Memory for Apach Spark Pool (GB) |`BigDataPoolAllocatedMemory` |Count |Maximum, Minimum, Average, Total |`SubmitterId`|PT1M |No|
|Apache Spark pool|**Active Apache Spark applications**<p><p>Total Active Apache Spark Pool Applications |`BigDataPoolApplicationsActive` |Count |Maximum, Minimum, Average |`JobState`|PT1M |No|
|Apache Spark pool|**Ended Apache Spark applications**<p><p>Count of Apache Spark pool applications ended |`BigDataPoolApplicationsEnded` |Count |Total |`JobType`, `JobResult`|PT1M |No|