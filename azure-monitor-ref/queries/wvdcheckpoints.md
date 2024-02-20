---
title: Example log table queries for WVDCheckpoints
description:  Example queries for WVDCheckpoints log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the WVDCheckpoints table


### Published remote resources by count of users  


Produces a bar chart of published resources by the number of users that have launched them.  

```query
// The checkpoints table keeps track of any individual remote application or desktop a user has started from the remote desktop client UI. 
// Note: These logs will only reflect applications published as RemoteApp; applications started within a published desktop session are not individually captured and only show as the overall remote desktop connection.
WVDCheckpoints  
| where Name == "LaunchExecutable" 
| extend App = parse_json(Parameters).filename 
| summarize Usage = dcount(UserName) by tostring(App) 
| sort by Usage desc 
| render barchart
```

