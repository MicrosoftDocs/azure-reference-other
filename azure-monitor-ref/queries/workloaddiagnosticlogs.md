---
title: Example log table queries for WorkloadDiagnosticLogs
description:  Example queries for WorkloadDiagnosticLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WorkloadDiagnosticLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Workload Monitoring Insights data collection warnings or errors  


Warning or error logs from data collection services of Workload Monitoring of Azure Monitor Insights.  

```query
WorkloadDiagnosticLogs
| where Status in ("Warning", "Error")
| sort by TimeGenerated desc
| take 100
```

