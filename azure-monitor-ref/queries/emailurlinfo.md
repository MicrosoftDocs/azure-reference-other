---
title: Example log table queries for EmailUrlInfo
description:  Example queries for EmailUrlInfo log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EmailUrlInfo table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### URLs in an email  


URLs in a particular message, by NetworkMessageId identifier.  

```query
let myEmailId = "<insert your email NetworkMessageId>";
EmailEvents
| where NetworkMessageId == myEmailId
| join EmailUrlInfo on NetworkMessageId
| project Timestamp, Subject, SenderFromAddress, RecipientEmailAddress, NetworkMessageId, Url, UrlCount 
| take 1000
```

