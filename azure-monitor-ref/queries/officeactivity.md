---
title: Example log table queries for OfficeActivity
description:  Example queries for OfficeActivity log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the OfficeActivity table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### All Office Activity  


All the events provided by Office Activity.  

```query
OfficeActivity
| project TimeGenerated, UserId, Operation, OfficeWorkload, RecordType, _ResourceId
| sort by TimeGenerated desc nulls last
```



### Users accessing files  


Users sorted by number of OneDrive and SharePoint files they accessed.  

```query
OfficeActivity
| where OfficeWorkload in ("OneDrive", "SharePoint") and Operation in ("FileDownloaded", "FileAccessed")
| summarize AccessedFilesCount = dcount(OfficeObjectId) by UserId, _ResourceId
| sort by AccessedFilesCount desc nulls last
```



### File upload operation  


Lists users sorted by number of files they uploaded to OneDrive and SharePoint.  

```query
OfficeActivity
| where OfficeWorkload in ("OneDrive", "SharePoint") and Operation in ("FileUploaded")
| summarize AccessedFilesCount = dcount(OfficeObjectId) by UserId, _ResourceId
| sort by AccessedFilesCount desc nulls last
```



### Office activity for user  


The query presents user's activity over Office.  

```query
// Replace the UPN in the query with the UPN of the user of interest
let v_Users_UPN= "osotnoc@contoso.com";
OfficeActivity
| where UserId==v_Users_UPN
| project TimeGenerated, OfficeWorkload, Operation, ResultStatus, OfficeObjectId, _ResourceId
```



### Creation of Forward rule  


Lists creation of email forward rules.  

```query
OfficeActivity
| where OfficeWorkload == "Exchange"
| where Operation in~ ("New-TransportRule", "Set-TransportRule")
| extend RuleName = case(Operation =~ "Set-TransportRule", tostring(OfficeObjectId), Operation =~ "New-TransportRule", tostring(parse_json(Parameters)[1].Value), "Unknown")
| project  TimeGenerated, ClientIP, UserId, Operation, RuleName, _ResourceId
```



### Suspicious file name  


Operations on files with name that might indicate obfuscation of an executable.  

```query
OfficeActivity
| where RecordType =~ "SharePointFileOperation" and isnotempty(SourceFileName)
| where OfficeObjectId has ".exe." and OfficeObjectId matches regex @"\.exe\.\w{0,4}$"
```

