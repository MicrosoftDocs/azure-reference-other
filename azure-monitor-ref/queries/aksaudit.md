---
title: Example log table queries for AKSAudit
description:  Example queries for AKSAudit log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AKSAudit table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Volume of Kubernetes audit events per SourceIp  


Display the count of Kubernetes audit events generated from a given source IP address for each AKS cluster. Requires Diagnostic Settings to use the Resource Specific destination table.  

```query
AKSAudit
| where ResponseStatus.code != 401  // Exclude unauthorized responses
| mv-expand SourceIps               // Expand the list of SourceIp entries into individual rows
| summarize Count = count() by SourceIp = tostring(SourceIps), ResourceId = _ResourceId
| sort by Count desc
```

