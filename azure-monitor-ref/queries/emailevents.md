---
title: Example log table queries for EmailEvents
description:  Example queries for EmailEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EmailEvents table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Phishing emails from the top 10 sender domains  


Get the number of phishing emails from the top ten sender domains.  

```query
EmailEvents
| where ThreatTypes has "Phish"
| summarize Count = count() by SenderFromDomain
| top 10 by Count 
```



### Emails with malware  


Get the number of phishing emails from the top ten sender domains.  

```query
EmailEvents
| where ThreatTypes has "Malware"
| limit 500 
```

