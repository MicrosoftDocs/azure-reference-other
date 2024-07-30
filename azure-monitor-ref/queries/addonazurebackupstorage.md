---
title: Example log table queries for AddonAzureBackupStorage
description:  Example queries for AddonAzureBackupStorage log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AddonAzureBackupStorage table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Trend of total Cloud Storage consumed  


View the daily trend of total (cumulative) Cloud Storage consumed.  

```query
// To create an alert for this query, click '+ New alert rule'
AddonAzureBackupStorage
| where OperationName == "StorageAssociation"
//Get total Cloud Storage being consumed per Backup Item at the end of each day
| summarize TotalStoragePerBackupItemPerDay=sum(StorageConsumedInMBs) by BackupItemUniqueId, Day=bin(TimeGenerated,1d), ResourceId
//Get total Cloud Storage being consumed at the end of each day
| summarize TotalStorage=sum(TotalStoragePerBackupItemPerDay) by Day, ResourceId
| sort by Day asc
| render timechart
```

