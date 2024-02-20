---
title: Example log table queries for KubePodInventory
description:  Example queries for KubePodInventory log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the KubePodInventory table


### Pods in crash loop  


Determines whether Pods/Containers has Crash-Loop phase.  

```query
//Determines whether Pods/Containers has Crash-Loop phase
KubePodInventory
| where ContainerStatus  == 'waiting' 
| where ContainerStatusReason == 'CrashLoopBackOff' or ContainerStatusReason == 'Error'
| extend ContainerLastStatus=todynamic(ContainerLastStatus)
| summarize RestartCount = arg_max(ContainerRestartCount, Computer, Namespace, ContainerLastStatus.reason) by Name
```



### Pods in pending state  


Check Pods that cannot be started and their pending time.  

```query
//Check Pods that cannot be started and its pending time
KubePodInventory
| where PodStatus == 'Pending'
| project PodCreationTimeStamp, Namespace, PodStartTime, PodStatus, Name, ContainerStatus
| summarize Start = any(PodCreationTimeStamp), arg_max(PodStartTime, Namespace) by Name
| extend PodStartTime = iff(isnull(PodStartTime), now(), PodStartTime)
| extend PendingTime = PodStartTime - Start
| project Name, Namespace ,PendingTime
```



### Find In KubePodInventory  


Find in KubePodInventory to search for a specific value in the KubePodInventory table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
KubePodInventory
| where * contains tostring(SearchValue)
| take 1000
```

