---
title: Example log table queries for AACHttpRequest
description:  Example queries for AACHttpRequest log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AACHttpRequest table


### Throttled Requests  


Lists of throttled requests to the App Config Service.  

```query
// This query helps retrieve logs for throttled requests during past one hour.
AACHttpRequest
| where StatusCode == 429 and TimeGenerated > ago(1h)
| sort by TimeGenerated desc

```



### Most common server errors  


Lists the most common error Status Code and a corresponding count.  

```query
// This query helps retrieve logs for failed requests during past one hour by status code. 
AACHttpRequest
| where StatusCode >= 500 and TimeGenerated > ago(1h)
| summarize ErrorCount=count() by StatusCode
| project StatusCode, ErrorCount
| sort by ErrorCount desc

```



### Most Active Clients by IP Address  


Lists the most common IP Addresses to communicate with the App Config Service.  

```query
// This query helps count requests by top 10 most active client IP addresses.  
AACHttpRequest
| summarize Count=count() by ClientIPAddress
| project ClientIPAddress, Count
| sort by Count desc
| limit 10

```

