---
title: Example log table queries for AzureActivity
description:  Example queries for AzureActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AzureActivity table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### [Classic] Find In AzureActivity  


[Classic] Find in AzureActivity to search for a specific value in the AzureActivity table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
AzureActivity
| where ResourceProvider == "MICROSOFT.KEYVAULT"
| where * contains tostring(SearchValue)
| take 1000
```



### Shut down Virtual Machines  


Virtual Machines successfully shut down in the last 10 minutes.  

```query
// To create an alert for this query, click '+ New alert rule'
AzureActivity
| where TimeGenerated > ago(10m)
| where OperationName == "Deallocate Virtual Machine" and ActivityStatus == "Succeeded" 

```



### Latest 50 logs  


Show the latest Azure Activity logs for this resource.  

```query
AzureActivity 
| top 50 by TimeGenerated desc 
```



### Operations' status  


Show the latest Azure activity log for each operation.  

```query
AzureActivity 
| summarize arg_max(TimeGenerated, *) by OperationName 
```



### Recent Azure Activity logs  


Display all Azure Activity logs from the last hour.  

```query
AzureActivity 
| where Level == "Error" or Level == "Warning"
| project TimeGenerated, Level, ResourceProvider, ActivityStatus, Caller, Category, Properties, CorrelationId 
```



### Failed operations  


List all reports of failed operations, over the past hour.  

```query
AzureActivity 
| where TimeGenerated > ago(1h)  
| where ActivityStatus == "Failed"
```



### Resources creation  


List created Azure resources. Can be useful for monitoring and alerts.  

```query
AzureActivity
| where OperationNameValue has "Microsoft.Resources/deployments/write"
| where CategoryValue == "Administrative"
| where ActivityStatusValue == "Success"
| project Caller, TimeGenerated, _ResourceId

```



### Find In AzureActivity  


Find in AzureActivity to search for a specific value in the AzureActivity table./nNote that this query requires updating the \<SeachValue\> parameter to produce results  

```query
// This query requires a parameter to run. Enter value in SearchValue to find in table.
let SearchValue =  "<SearchValue>";//Please update term you would like to find in the table.
AzureActivity
| where ResourceProvider == "Microsoft.ContainerService"
| where * contains tostring(SearchValue)
| take 1000
```



### Show logs from AzureActivity table  


Lists the latest logs in AzureActivity table, sorted by time (latest first).  

```query
AzureActivity
| top 10 by TimeGenerated
```



### Show logs from AzureActivity table  


Lists the latest logs in AzureActivity table, sorted by time (latest first).  

```query
AzureActivity
| top 10 by TimeGenerated
```



### Display top 50 Activity log events  


Display top 50 Activity log events.  

```query
AzureActivity
| project TimeGenerated, SubscriptionId, ResourceGroup,ResourceProviderValue,OperationNameValue,CategoryValue,CorrelationId,ActivityStatusValue, ActivitySubstatusValue, Properties_d, Caller
| top 50 by TimeGenerated
```



### Display Activity log Administrative events  


Displays Activity log for Administrative category.  

```query
AzureActivity 
| where CategoryValue == "Administrative"
| order by TimeGenerated desc
```



### VM creation  


This query displays results of when a VM is created.  

```query
AzureActivity
| where TimeGenerated >= ago(1d)
| where OperationNameValue == "MICROSOFT.COMPUTE/VIRTUALMACHINES/WRITE" and ActivityStatusValue == "Start"
| where Authorization_d.action == "Microsoft.Compute/virtualMachines/write"
| project OperationNameValue, ActivityStatusValue, VM_Name=Properties_d.resource, ResourceGroup, SubscriptionId, Created_By=Caller
```



### Display Activity log events generated from Policy  


Display top 100 records of all effect action operations performed by Azure Policy.  

```query
AzureActivity
| project TimeGenerated, SubscriptionId, ResourceProviderValue, OperationNameValue, Caller, CategoryValue, CorrelationId, ActivityStatusValue, Properties_d
| where OperationNameValue has "audit"
| top 100 by TimeGenerated desc
```



### List callers and their associated action in last 48 hours  


List callers and their associated action in last 48 hours.  

```query
AzureActivity
| where TimeGenerated > ago(2d)
| project Caller, OperationNameValue, ActivityStatusValue, CategoryValue
| where Caller has "@"
```



### All Azure Activity  


The query presents all AzureActivity events.  

```query
AzureActivity
| project TimeGenerated, Caller, OperationName, ActivityStatus, _ResourceId
```



### Azure Activity for user  


Show the user's activity over Azure Activity.  

```query
// Replace the UPN in the query with the UPN of the user of interest
let v_Users_UPN= "osotnoc@contoso.com";
AzureActivity
| where Caller == v_Users_UPN
| project TimeGenerated, Caller, OperationName, ActivityStatus
```



### Successful key enumaration  


Lists users who performed key enumeration, and their location.  

```query
AzureActivity
| where OperationName == "List Storage Account Keys"
| where ActivityStatus == "Succeeded"
| project TimeGenerated, Caller, CallerIpAddress, OperationName
```



### Network Access JIT initiation  


Lists the initiation of JIT network access permissions.  

```query
AzureActivity
| where OperationName == "Initiate JIT Network Access Policy"
| where ActivityStatus == "Started"
```



### Azure Activity operation statistics  


Statistics of operations over Azure Activity.  

```query
AzureActivity
| summarize Count=count() by OperationName, _ResourceId
| sort by Count desc nulls last
```

