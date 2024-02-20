---
title: Example log table queries for Update
description:  Example queries for Update log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the Update table


### Missing security or critical updates  


Count how many security or other critical updates are missing.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
| where Classification in ("Security Updates", "Critical Updates")
| where UpdateState == 'Needed' and Optional == false and Approved == true
| summarize count() by Classification, Computer, _ResourceId
// This query requires the Security or Update solutions
```



### Updates available for Windows machines  


List the Windows update KBIDs available by their classification and for each Computer.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
| where TimeGenerated>ago(14h) 
| where UpdateState =~ "Needed" and OSType != "Linux" 
| summarize by Computer, Classification, Product, KBID, ResourceId
```



### Updates available for Linux machines  


List the Linux package version updates available by their classification and for each Computer.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
| where TimeGenerated>ago(14h) 
| where UpdateState =~ "Needed" and OSType == "Linux" 
| summarize by Computer, Classification, Product, ProductVersion, ResourceId
```



### Missing updates summary  


Get a summary of missing updates by category.  

```query
Update
| where TimeGenerated>ago(5h) and OSType=="Linux" and SourceComputerId in ((Heartbeat
| where TimeGenerated>ago(12h) and OSType=="Linux" and notempty(Computer)
| summarize arg_max(TimeGenerated, Solutions) by SourceComputerId
| where Solutions has "updates"
| distinct SourceComputerId))
| summarize hint.strategy=partitioned arg_max(TimeGenerated, UpdateState, Classification) by Computer, SourceComputerId, Product, ProductArch
| where UpdateState=~"Needed"
| summarize by Product, ProductArch, Classification
| union (Update
| where TimeGenerated>ago(14h) and OSType!="Linux" and (Optional==false or Classification has "Critical" or Classification has "Security") and SourceComputerId in ((Heartbeat
| where TimeGenerated>ago(12h) and OSType=~"Windows" and notempty(Computer)
| summarize arg_max(TimeGenerated, Solutions) by SourceComputerId
| where Solutions has "updates"
| distinct SourceComputerId))
| summarize hint.strategy=partitioned arg_max(TimeGenerated, UpdateState, Classification, Approved) by Computer, SourceComputerId, UpdateID
| where UpdateState=~"Needed" and Approved!=false
| summarize by UpdateID, Classification )
| summarize allUpdatesCount=count(), criticalUpdatesCount=countif(Classification has "Critical"), securityUpdatesCount=countif(Classification has "Security"), otherUpdatesCount=countif(Classification !has "Critical" and Classification !has "Security")
```



### Missing updates list  


Get a list of all updates that are missing.  

```query
Update
| where TimeGenerated>ago(5h) and OSType=="Linux" and SourceComputerId in ((Heartbeat
| where TimeGenerated>ago(12h) and OSType=="Linux" and notempty(Computer)
| summarize arg_max(TimeGenerated, Solutions) by SourceComputerId
| where Solutions has "updates"
| distinct SourceComputerId))
| summarize hint.strategy=partitioned arg_max(TimeGenerated, UpdateState, Classification, BulletinUrl, BulletinID) by SourceComputerId, Product, ProductArch
| where UpdateState=~"Needed"
| project-away UpdateState, TimeGenerated
| summarize computersCount=dcount(SourceComputerId, 2), ClassificationWeight=max(iff(Classification has "Critical", 4, iff(Classification has "Security", 2, 1))) by id=strcat(Product, "_", ProductArch), displayName=Product, productArch=ProductArch, classification=Classification, InformationId=BulletinID, InformationUrl=tostring(split(BulletinUrl, ";", 0)[0]), osType=1
| union(Update
| where TimeGenerated>ago(14h) and OSType!="Linux" and (Optional==false or Classification has "Critical" or Classification has "Security") and SourceComputerId in ((Heartbeat
| where TimeGenerated>ago(12h) and OSType=~"Windows" and notempty(Computer)
| summarize arg_max(TimeGenerated, Solutions) by SourceComputerId
| where Solutions has "updates"
| distinct SourceComputerId))
| summarize hint.strategy=partitioned arg_max(TimeGenerated, UpdateState, Classification, Title, KBID, PublishedDate, Approved) by Computer, SourceComputerId, UpdateID
| where UpdateState=~"Needed" and Approved!=false
| project-away UpdateState, Approved, TimeGenerated
| summarize computersCount=dcount(SourceComputerId, 2), displayName=any(Title), publishedDate=min(PublishedDate), ClassificationWeight=max(iff(Classification has "Critical", 4, iff(Classification has "Security", 2, 1))) by id=strcat(UpdateID, "_", KBID), classification=Classification, InformationId=strcat("KB", KBID), InformationUrl=iff(isnotempty(KBID), strcat("https://support.microsoft.com/kb/", KBID), ""), osType=2)
| sort by ClassificationWeight desc, computersCount desc, displayName asc
| extend informationLink=(iff(isnotempty(InformationId) and isnotempty(InformationUrl), toobject(strcat('{ "uri": "', InformationUrl, '", "text": "', InformationId, '", "target": "blank" }')), toobject('')))
| project-away ClassificationWeight, InformationId, InformationUrl
```



### Computer with missing updates  


All computers with missing updates.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
|where OSType != "Linux" and UpdateState == "Needed" and Optional == "false" 
| project TimeGenerated, Computer, Title, KBID, Classification, MSRCSeverity, PublishedDate, _ResourceId
| sort by TimeGenerated desc
```



### Missing required updates for server  


Missing updates for a specific computer "ComputerName" (replace with your own computer name).  

```query
// To create an alert for this query, click '+ New alert rule'
let ComputerName = "Enter your computer name here";
Update
|where OSType != "Linux" and UpdateState == "Needed" and Optional == "false" and Computer == ComputerName
| project TimeGenerated, Computer, Title, KBID, Product, MSRCSeverity, PublishedDate, _ResourceId
| sort by TimeGenerated desc
```



### Missing critical security updates  


All computers that are missing critical updates or security updates.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
|where  OSType != "Linux" and UpdateState == "Needed" and Optional == "false" and (Classification == "Security Updates" or Classification == "Critical Updates") 
| sort by TimeGenerated desc 
```



### Missing security or critical where update is manual  


Critical or security updates needed by machines where updates are manually applied.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
| where OSType != "Linux" and UpdateState == "Needed" and Optional == "false"
 |where (Classification == "Security Updates" or Classification == "Critical Updates")
| join kind=inner (UpdateSummary |where WindowsUpdateSetting == "Manual" |distinct Computer) on Computer 
| distinct KBID, Computer, _ResourceId
```



### Missing update rollups  


All computers with missing update rollups.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
| where OSType != "Linux" and Optional == "false" and Classification == "Update Rollups" and UpdateState == "Needed" 
| project TimeGenerated, Computer, Title, KBID, Classification, MSRCSeverity, PublishedDate, _ResourceId
| sort by TimeGenerated desc
```



### Distinct missing updates cross computers  


Distinct missing updates across all computers.  

```query
// To create an alert for this query, click '+ New alert rule'
Update
| where OSType != "Linux" and UpdateState == "Needed" and Optional == "false" 
| distinct Title, Computer, _ResourceId
```

