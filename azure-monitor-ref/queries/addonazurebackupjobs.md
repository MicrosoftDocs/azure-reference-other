---
title: Example log table queries for AddonAzureBackupJobs
description:  Example queries for AddonAzureBackupJobs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AddonAzureBackupJobs table


### Distribution of Backup Jobs by Status  


View the number of completed and failed Backup Jobs in the selected time range.  

```query
AddonAzureBackupJobs
//Get all Backup Jobs
| where JobOperation  == "Backup"
//Remove duplicate records if any
| summarize arg_max(TimeGenerated, *) by JobUniqueId
//Summarize by Job Status
| summarize count(JobUniqueId) by JobStatus
```



### Distribution of Restore Jobs by Status  


View the number of completed and failed Restore Jobs in the selected time range.  

```query
AddonAzureBackupJobs
//Get all Restore Jobs
| where JobOperation  in~ ("Restore","Recovery") 
//Remove duplicate records if any
| summarize arg_max(TimeGenerated, *) by JobUniqueId
//Summarize by Job Status
| summarize count(JobUniqueId) by JobStatus
```



### All Successful Jobs  


View all successful jobs in the selected time range.  

```query
AddonAzureBackupJobs
| summarize arg_max(TimeGenerated,*) by JobUniqueId
| where JobStatus == "Completed" 
```



### All Failed Jobs  


View all failed jobs in the selected time range.  

```query
// To create an alert for this query, click '+ New alert rule'
AddonAzureBackupJobs
| summarize arg_max(TimeGenerated,*) by JobUniqueId
| where JobStatus == "Failed"
```

