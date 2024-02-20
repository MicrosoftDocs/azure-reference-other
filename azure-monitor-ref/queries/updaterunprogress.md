---
title: Example log table queries for UpdateRunProgress
description:  Example queries for UpdateRunProgress log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the UpdateRunProgress table


### Patch installation failure for your machines  


List for each machine the installation status of the updates where the installation was not successful.  

```query
// To create an alert for this query, click '+ New alert rule'
UpdateRunProgress
| where TimeGenerated>ago(1d) 
| where InstallationStatus == "NotStarted" 
| summarize by Title, InstallationStatus, SourceComputerId, UpdateId, Computer, ResourceId
| join kind= inner (
    UpdateRunProgress
    | where TimeGenerated>ago(1d) 
    | where InstallationStatus != "NotStarted" 
    | summarize by Title, InstallationStatus, SourceComputerId, UpdateId, Computer
) on UpdateId 
| where InstallationStatus1 != "Succeed"
| summarize by Title, InstallationStatus, Computer, ResourceId

```

