---
title: Example log table queries for AVNMNetworkGroupMembershipChange
description:  Example queries for AVNMNetworkGroupMembershipChange log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AVNMNetworkGroupMembershipChange table


### Get recent Network Group Membership changes  


List 10 most recent Network Group Membership changes.  

```query
//GroupMemberships column would have list of NetworkGroupIds and the respective MembershipDetails(Membership type - Static/Policy and their respective Ids) which NetworkResourceIds are part of.
AVNMNetworkGroupMembershipChange
|top 10 by TimeGenerated desc
|project TimeGenerated, NetworkResourceIds, GroupMemberships, ResultType

```



### Failed Network Group Membership Changes  


List failed Network Group Membership changes.  

```query
AVNMNetworkGroupMembershipChange
|where ResultType != "Success"
|sort by TimeGenerated desc
|take 100

```

