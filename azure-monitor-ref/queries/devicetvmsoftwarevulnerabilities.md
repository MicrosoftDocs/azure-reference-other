---
title: Example log table queries for DeviceTvmSoftwareVulnerabilities
description:  Example queries for DeviceTvmSoftwareVulnerabilities log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the DeviceTvmSoftwareVulnerabilities table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Devices affected by a specific vulnerability  


List devices affected by a specific vulnerability.  

```query
DeviceTvmSoftwareVulnerabilities
| where CveId == 'CVE-2020-0791'
| limit 100 
```

