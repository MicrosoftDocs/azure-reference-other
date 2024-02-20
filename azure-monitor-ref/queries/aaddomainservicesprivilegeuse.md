---
title: Example log table queries for AADDomainServicesPrivilegeUse
description:  Example queries for AADDomainServicesPrivilegeUse log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADDomainServicesPrivilegeUse table


### Show logs from AADDomainServicesPrivilegeUse table  


Lists the latest logs in AADDomainServicesPrivilegeUse table, sorted by time (latest first).  

```query
AADDomainServicesPrivilegeUse
| top 10 by TimeGenerated
```

