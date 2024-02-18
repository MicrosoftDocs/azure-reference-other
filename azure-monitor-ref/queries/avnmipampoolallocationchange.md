---
title: Example log table queries for AVNMIPAMPoolAllocationChange
description:  Example queries for AVNMIPAMPoolAllocationChange log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AVNMIPAMPoolAllocationChange table


### AVNM IPAM pool allocation changes  


List 10 most recent Azure Virtual Network Manager (AVNM) IPAM pool allocation additions, removals, and updates. Pool allocations include child pools, static cidrs, and resource associations.  

```query
AVNMIPAMPoolAllocationChange
| top 10 by TimeGenerated desc
| project TimeGenerated, ChangeType, ChangeReason, AllocationResources, ResultType
```



### Failed AVNM IPAM pool allocation changes  


List 100 most recent failures in Azure Virtual Network Manager (AVNM) IPAM pool allocation additions, removals, and updates. Pool allocations include child pools, static cidrs, and resource associations  

```query
AVNMIPAMPoolAllocationChange
| where ResultType != "Success"
| sort by TimeGenerated desc
| take 100
```

