---
title: Example log table queries for MicrosoftGraphActivityLogs
description:  Example queries for MicrosoftGraphActivityLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the MicrosoftGraphActivityLogs table


### Frequent users endpoint callers  


Gets list of apps and service principals calling users endpoint.  

```query
MicrosoftGraphActivityLogs
| where RequestUri has "users"
| summarize NumRequests=count() by AppId, ServicePrincipalId, UserId
| sort by NumRequests desc
| limit 100
```



### Failed groups endpoint requests  


Gets a list of failed requests to group entities, by apps and service principals.  

```query
MicrosoftGraphActivityLogs
| where ResponseStatusCode == 403
| where RequestUri has "groups"
| summarize UniqueRequests=dcount(RequestId) by AppId, ServicePrincipalId, UserId
| sort by UniqueRequests desc
| limit 100
```

