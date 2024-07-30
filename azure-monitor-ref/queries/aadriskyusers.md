---
title: Example log table queries for AADRiskyUsers
description:  Example queries for AADRiskyUsers log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADRiskyUsers table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### High risk users  


Gets list of the top 100 at high risk users for the last day.  

```query
AADRiskyUsers
| where RiskLastUpdatedDateTime > ago(1d)
| where RiskLevel == "high"
| where RiskState == "atRisk"
| take 100
```

