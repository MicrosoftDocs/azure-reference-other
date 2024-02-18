---
title: Example log table queries for AzureLoadTestingOperation
description:  Example queries for AzureLoadTestingOperation log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AzureLoadTestingOperation table


### Azure load test creation count  


Counts the number of tests creation by resource ID.  

```query
AzureLoadTestingOperation
| where OperationId == "Test_CreateOrUpdateTest"
| where HttpStatusCode == 201
| summarize count() by _ResourceId
```



### Azure load test run creation count  


Counts the number of successful test runs started by resource ID.  

```query
AzureLoadTestingOperation
| where OperationId == "TestRun_CreateAndUpdateTest"
| where HttpStatusCode == 200
| summarize count() by _ResourceId
```

