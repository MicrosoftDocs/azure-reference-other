---
title: Example log table queries for ASimDnsActivityLogs
description:  Example queries for ASimDnsActivityLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ASimDnsActivityLogs table


### Count DNS failures for a source by source and type  


Count the number of failed DNS queries for each source IP address and failure type  

```query
ASimDnsActivityLogs
| where EventType == 'Query' and EventResult == 'Failure'
| summarize count() by SrcIpAddr, EventResultDetails
```



### Identify excessive query for a nonexistent domain by a source  


Count the number of queries that return NXDOMAIN, indicating that the queries domain name does not exist, and compares the count to a threshold of 100.  

```query
ASimDnsActivityLogs
| where EventResultDetails == 'NXDOMAIN'
| summarize c=count() by SrcIpAddr
| where c > 100
```

