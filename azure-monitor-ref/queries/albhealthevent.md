---
title: Example log table queries for ALBHealthEvent
description:  Example queries for ALBHealthEvent log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 05/22/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ALBHealthEvent table


### Latest Snat Port Exhaustion Per LB Frontend  


List the latest SNAT port exhaustion event per load balancer Frontend IP  

```query
ALBHealthEvent
| where TimeGenerated > ago(1d)
| where HealthEventType == "SnatPortExhaustion"
| summarize arg_max(TimeGenerated, *) by LoadBalancerResourceId, FrontendIP
```

