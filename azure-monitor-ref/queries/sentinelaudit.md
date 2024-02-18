---
title: Example log table queries for SentinelAudit
description:  Example queries for SentinelAudit log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the SentinelAudit table


### Failures updating Office365-Sharepoint related Sentinel resources  


Display audit logs of failed attempts to update Office365-Sharepoint related Sentinel resources, with an optional filter by caller name and workspace id.  

```query
SentinelAudit
//| where WorkspaceId == "<WorkspaceId>"  // to filter on a specific WorspaceId, uncomment this line
| extend CallerName = tostring(ExtendedProperties.CallerName)
// | where CallerName startswith "<userName>" // to to filter on a specific user, uncomment this line
| where Status == "Failure"
| where SentinelResourceName has "Office365-Sharepoint"
| limit 100
```

