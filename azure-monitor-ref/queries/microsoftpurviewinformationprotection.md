---
title: Example log table queries for MicrosoftPurviewInformationProtection
description:  Example queries for MicrosoftPurviewInformationProtection log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MicrosoftPurviewInformationProtection table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Microsoft Purview Information Protection events  


Microsoft Purview Information Protection events summarized by label event type and workload.  

```query
MicrosoftPurviewInformationProtection
| summarize Value=count() by LabelEventType, Workload
| order by Value
```

