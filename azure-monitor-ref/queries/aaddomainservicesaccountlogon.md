---
title: Example log table queries for AADDomainServicesAccountLogon
description:  Example queries for AADDomainServicesAccountLogon log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADDomainServicesAccountLogon table


### Show logs from AADDomainServicesAccountLogon table  


Lists the latest logs in AADDomainServicesAccountLogon table, sorted by time (latest first).  

```query
AADDomainServicesAccountLogon
| top 10 by TimeGenerated
```

