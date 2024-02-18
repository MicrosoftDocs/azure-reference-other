---
title: Example log table queries for ACRConnectedClientList
description:  Example queries for ACRConnectedClientList log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACRConnectedClientList table


### Unique Redis client IP addresses  


Unique Redis client IP addresses that have connected to the cache.  

```query
ACRConnectedClientList
| summarize count() by ClientIp

```



### Redis client connections per hour  


Redis client connections per hour within the specified IP address range.  

```query
let IpRange = "10.1.1.0/24";
ACRConnectedClientList
// For particular datetime filtering, add '| where TimeGenerated between (StartTime .. EndTime)'
| where ipv4_is_in_range(ClientIp, IpRange)
| summarize ConnectionCount = sum(ClientCount) by TimeRange = bin(TimeGenerated, 1h)

```

