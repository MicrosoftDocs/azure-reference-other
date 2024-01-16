---
ms.service: azure-monitor
ms.topic: include
ms.date: 01/10/2024
ms.author: edbaynash
author: EdB-MSFT
ms.custom: Microsoft.VoiceServices/CommunicationsGateways, naam

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 
 
---

  
  
|Category|Metric|Name in REST API|Unit|Aggregation|Dimensions|Time Grains|DS Export|
|---|---|---|---|---|---|---|---|
|Error|**Active Call Failures**<p><p>Percentage of active call failures |`ActiveCallFailures` |Percent |Average, Minimum, Maximum |`Region`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Traffic|**Active Calls**<p><p>Count of the total number of active calls (signaling sessions) |`ActiveCalls` |Count |Average, Minimum, Maximum |`Region`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|
|Traffic|**Active Emergency Calls**<p><p>Count of the total number of active emergency calls |`ActiveEmergencyCalls` |Count |Average, Minimum, Maximum |`Region`|PT1M, PT5M, PT15M, PT30M, PT1H, PT6H, PT12H, P1D |No|