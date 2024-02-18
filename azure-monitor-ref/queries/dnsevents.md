---
title: Example log table queries for DnsEvents
description:  Example queries for DnsEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DnsEvents table


### Clients Resolving Malicious Domains  


Distinct clients resolving malicious domains.  

```query
DnsEvents
| where SubType == 'LookupQuery' and isnotempty(MaliciousIP)
| summarize count() by ClientIP
```

