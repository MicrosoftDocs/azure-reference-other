---
title: Example log table queries for CoreAzureBackup
description:  Example queries for CoreAzureBackup log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the CoreAzureBackup table


### Backup Items by Vault and Backup item type  


View the different types of items being backed up.  

```query
CoreAzureBackup
//get all backup items
| where OperationName == "BackupItem"
//remove duplicate records if any
| summarize arg_max(TimeGenerated, *) by BackupItemUniqueId, ResourceId
// summarize backup items by type
| summarize NumberOfItems=count(BackupItemUniqueId) by BackupItemType
```

