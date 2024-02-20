---
title: Example log table queries for AegPublishFailureLogs
description:  Example queries for AegPublishFailureLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AegPublishFailureLogs table


### Publish failures by topic and error  


Publish failures logs by topic name and error message.  

```query
AegPublishFailureLogs 
| parse Message with * "), httpStatusCode=" HttpStatusCode "," * ", errorMessage=" ErrorMessage 
| parse _ResourceId with * "/topics/" TopicName 
| project TimeGenerated, _ResourceId, TopicName, TenantId, OperationName, HttpStatusCode, ErrorMessage
| summarize by _ResourceId, TopicName, HttpStatusCode, ErrorMessage
```



### Publish failures by topic and error  


Publish failures logs by topic name and error message.  

```query
// To create an alert for this query, click '+ New alert rule'
AegPublishFailureLogs 
| parse Message with * "), httpStatusCode=" HttpStatusCode "," * ", errorMessage=" ErrorMessage 
| parse _ResourceId with * "/topics/" TopicName 
| project TimeGenerated, _ResourceId, TopicName, TenantId, OperationName, HttpStatusCode, ErrorMessage
| summarize by _ResourceId, TopicName, HttpStatusCode, ErrorMessage
```



### Publish failures by domain and error  


Publish failures logs by domain name and error message.  

```query
// To create an alert for this query, click '+ New alert rule'
AegPublishFailureLogs 
| parse Message with * "), httpStatusCode=" HttpStatusCode "," * ", errorMessage=" ErrorMessage 
| parse _ResourceId with * "/domains/" DomainName
| project TimeGenerated, _ResourceId, DomainName, TenantId, OperationName, HttpStatusCode, ErrorMessage
| summarize by _ResourceId, DomainName, HttpStatusCode, ErrorMessage
```

