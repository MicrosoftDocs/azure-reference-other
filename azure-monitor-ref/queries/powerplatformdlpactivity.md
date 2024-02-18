---
title: Example log table queries for PowerPlatformDlpActivity
description:  Example queries for PowerPlatformDlpActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the PowerPlatformDlpActivity table


### Power Platform DLP events filtered by by activity type  


Display events from more than one day ago, filtered by CreateDlpPolicy activity type and summarized by user ID, policy name and policy type.  

```query
PowerPlatformDlpActivity
| where EventOriginalType == "CreateDlpPolicy"
| extend PolicyType = tostring(AdditionalInfo.policyType)
| summarize count() by EventOriginalType, ActorName, PolicyName, PolicyType
```

