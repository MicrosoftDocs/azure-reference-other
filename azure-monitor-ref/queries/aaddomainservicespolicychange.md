---
title: Example log table queries for AADDomainServicesPolicyChange
description:  Example queries for AADDomainServicesPolicyChange log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AADDomainServicesPolicyChange table


### Show logs from AADDomainServicesPolicyChange table  


Lists the latest logs in AADDomainServicesPolicyChange table, sorted by time (latest first).  

```query
AADDomainServicesPolicyChange
| top 10 by TimeGenerated
```

