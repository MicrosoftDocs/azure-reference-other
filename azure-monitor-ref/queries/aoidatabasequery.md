---
title: Example log table queries for AOIDatabaseQuery
description:  Example queries for AOIDatabaseQuery log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AOIDatabaseQuery table


### Queries executed by a user on dataproduct  


List all the queries run on a dataproduct by a particular user.  

```query
AOIDatabaseQuery
| where DatabaseName has_cs "edrdp" and User has_cs "username@domain.com"
| take 100
```

