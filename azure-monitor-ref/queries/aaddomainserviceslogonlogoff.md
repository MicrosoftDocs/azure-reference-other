---
title: Example log table queries for AADDomainServicesLogonLogoff
description:  Example queries for AADDomainServicesLogonLogoff log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADDomainServicesLogonLogoff table


### Show logs from AADDomainServicesLogonLogoff table  


Lists the latest logs in AADDomainServicesLogonLogoff table, sorted by time (latest first).  

```query
AADDomainServicesLogonLogoff
| top 10 by TimeGenerated
```

