---
title: Example log table queries for AVNMRuleCollectionChange
description:  Example queries for AVNMRuleCollectionChange log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AVNMRuleCollectionChange table


### Get recent security admin rule collection changes  


List 10 most recent security admin rule collection changes.  

```query
AVNMRuleCollectionChange
|where OperationName has("securityAdminRuleCollections")
|top 10 by TimeGenerated desc
|project TimeGenerated, NetworkResourceIds, AppliedRuleCollectionIds, ResultType
```



### Get recent failed security admin rule collection changes  


List 100 most recent failed security admin rule collection changes.  

```query
AVNMRuleCollectionChange
|where OperationName has("securityAdminRuleCollections")
|where ResultType != "Success"
|sort by TimeGenerated desc
|take 100

```

