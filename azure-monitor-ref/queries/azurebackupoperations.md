---
title: Example log table queries for AzureBackupOperations
description:  Example queries for AzureBackupOperations log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AzureBackupOperations table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Get all backup operations  


Get all backup operations for change passphrase.  

```query
AzureBackupOperations
//| where TimeGenerated >= ago(30d) // uncomment this line to view last 30 days
| where OperationType == "ChangePassphrase"
| project TimeGenerated, OperationType, OperationStartTime, ExtendedProperties, BackupManagementType
| limit 10
```

