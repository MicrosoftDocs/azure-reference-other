---
title: Example log table queries for AZFWApplicationRule
description:  Example queries for AZFWApplicationRule log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZFWApplicationRule table


### Application rule logs  


Connections that matched Application rules. HTTP, HTTPS and MSSQL are supported. Both connection and rule metadata is displayed.  

```query
AZFWApplicationRule
| take 100

```



### All firewall decisions  


All decision taken by firewall. Contains hits on network, application and NAT rules, as well as threat intelligence hits and IDPS signature hits.  

```query
AZFWNetworkRule
| union AZFWApplicationRule, AZFWNatRule, AZFWThreatIntel, AZFWIdpsSignature
| take 100
```

