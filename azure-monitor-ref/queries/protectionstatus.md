---
title: Example log table queries for ProtectionStatus
description:  Example queries for ProtectionStatus log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ProtectionStatus table


### Signatures out of date  


Devices with Signatures out of date.  

```query
// To create an alert for this query, click '+ New alert rule'
ProtectionStatus
| summarize Rank = max(ProtectionStatusRank) by Computer, _ResourceId
| where Rank == "250"
```



### Protection Status updates  


Protection Status updates per day.  

```query
// To create an alert for this query, click '+ New alert rule'
ProtectionStatus
| summarize AggregatedValue = count(ScanDate) by bin(TimeGenerated, 1d), Computer, _ResourceId
| sort by TimeGenerated desc
```



### Malware detection  


Malware detected grouped by threat.  

```query
// To create an alert for this query, click '+ New alert rule'
ProtectionStatus
| where ThreatStatus != "No threats detected" 
| summarize AggregatedValue = count() by Threat, Computer, _ResourceId
```

