---
title: Example log table queries for ACREntraAuthenticationAuditLog
description:  Example queries for ACREntraAuthenticationAuditLog log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 09/02/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACREntraAuthenticationAuditLog table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Microsoft Entra authentication audit log  


Logging Microsoft Entra authentication audit events.  

```query
source
| project
    TimeGenerated = todatetime(['time']),
    Location = location,
    OperationName = operationName,
    CacheName = tostring(properties.tenant),
    Message = tostring(properties.message),
    Authentication = tostring(properties.authentication),
    Username = tostring(properties.username),
    IpAddress = tostring(properties.ipAddress),
    ClientId = tostring(properties.clientId),
    ClientName = tostring(properties.clientName),
    Lifetime = tostring(properties.lifetime),
    RoleInstance = toint(properties.roleInstance)
```

