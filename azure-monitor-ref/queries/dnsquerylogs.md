---
title: Example log table queries for DNSQueryLogs
description:  Example queries for DNSQueryLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DNSQueryLogs table


### DNS queries by virtual network and return code  


Summarize count of DNS queries by virtual network and return code.  

```query
DNSQueryLogs
| summarize count() by VirtualNetworkId, ResponseCode
```

