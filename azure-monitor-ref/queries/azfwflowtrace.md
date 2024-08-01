---
title: Example log table queries for AZFWFlowTrace
description:  Example queries for AZFWFlowTrace log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZFWFlowTrace table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Azure Firewall flow trace logs  


Identify flow traces across Azure Firewall instances. Log contains flow information, flags and the time period when the flows were recorded.  

```query
AZFWFlowTrace
| where Flag == "INVALID"
| order by TimeGenerated desc
| take 100

```

