---
title: Example log table queries for NGXSecurityLogs
description:  Example queries for NGXSecurityLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/01/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the NGXSecurityLogs table


### Show NGINXaaS security logs  


A list of security logs sorted by time.  

```query
NGXSecurityLogs
| where FilePath == "/var/log/nginx/security.log"
| sort by TimeGenerated asc
| take 100
```

