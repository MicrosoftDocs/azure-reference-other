---
title: Example log table queries for AZFWFlowTrace
description:  Example queries for AZFWFlowTrace log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZFWFlowTrace table


### Azure Firewall flow trace logs  


Identify flow traces across Azure Firewall instances. Log contains flow information, flags and the time period when the flows were recorded.  

```query
AZFWFlowTrace
| where Flag == "INVALID"
| order by TimeGenerated desc
| take 100

```

