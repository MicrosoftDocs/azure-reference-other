---
title: Example log table queries for CHSMManagementAuditLogs
description:  Example queries for CHSMManagementAuditLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CHSMManagementAuditLogs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Aggregate operations query  


List logs for specific HSM partition operations.  

```query
CHSMManagementAuditLogs
| where OperationName == "END_MARKER_OPCODE (0xffff)/SPECIAL (0xffff)" 
| where OperationName == "CN_GENERATE_KEY_PAIR (0x19)/CN_MGMT_CMD (0x0)"
| sort by TimeGenerated desc 
| limit 100

```



### Failed operations count  


Count of failed HSM partition operations requests by userId, operationName and opCode.  

```query
CHSMManagementAuditLogs
| where not(Response contains "FAIL")
| summarize count() by TimeGenerated, UserId, OperationName, Opcode
```



### Operations per user  


Count of total HSM partition operations performed per user.  

```query
CHSMManagementAuditLogs
| summarize count() by UserId

```

