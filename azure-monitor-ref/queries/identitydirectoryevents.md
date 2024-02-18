---
title: Example log table queries for IdentityDirectoryEvents
description:  Example queries for IdentityDirectoryEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the IdentityDirectoryEvents table


### Group Membership changed  


Group Membership changed.  

```query
let group = '<insert your group>';
IdentityDirectoryEvents
| where ActionType == 'Group Membership changed'
| extend AddedToGroup = AdditionalFields['TO.GROUP']
| extend RemovedFromGroup = AdditionalFields['FROM.GROUP']
| extend TargetAccount = AdditionalFields['TARGET_OBJECT.USER']
| where AddedToGroup == group or RemovedFromGroup == group
| project-reorder Timestamp, ActionType, AddedToGroup, RemovedFromGroup, TargetAccount
| limit 100
```



### Password change event  


Find the latest password change event for a specific account.  

```query
//Find the latest password change event for a specific account
let userAccount = '<insert your user account>';
let deviceAccount = 'insert your device account';
IdentityDirectoryEvents
| where ActionType == 'Account Password changed'
| where TargetAccountDisplayName == userAccount
//If you are looking for last password change of a device account comment the above row and remove comment from the below row
//| where TargetDeviceName == deviceAccount
| summarize LastPasswordChangeTime = max(Timestamp) by TargetAccountDisplayName // or change to TargetDeviceName for devcie account
```

