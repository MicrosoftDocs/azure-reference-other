---
title: Example log table queries for AZMSDiagnosticErrorLogs
description:  Example queries for AZMSDiagnosticErrorLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 04/15/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AZMSDiagnosticErrorLogs table


### Publish detailed error logs  


Publish detailed error logs for diagnostics.  

```query
AZMSDiagnosticErrorLogs
| where Provider =~ "EventHub"
| project  ActivityName, _ResourceId, OperationResult,errorMessage
| summarize by ActivityName
```



### Publish detailed error logs  


Publish detailed error logs for diagnostics.  

```query
AZMSDiagnosticErrorLogs
| where Provider =~ "Relay"
| project  ActivityName, _ResourceId, OperationResult,errorMessage
| summarize by ActivityName
```



### Publish detailed error logs  


Publish detailed error logs for diagnostics.  

```query
AZMSDiagnosticErrorLogs
| where Provider =~ "ServiceBus"
| project  ActivityName, _ResourceId, OperationResult,errorMessage
| summarize by ActivityName
```

