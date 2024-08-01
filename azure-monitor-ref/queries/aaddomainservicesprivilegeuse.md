---
title: Example log table queries for AADDomainServicesPrivilegeUse
description:  Example queries for AADDomainServicesPrivilegeUse log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADDomainServicesPrivilegeUse table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Show logs from AADDomainServicesPrivilegeUse table  


Lists the latest logs in AADDomainServicesPrivilegeUse table, sorted by time (latest first).  

```query
AADDomainServicesPrivilegeUse
| top 10 by TimeGenerated
```

