---
title: Example log table queries for AlertEvidence
description:  Example queries for AlertEvidence log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AlertEvidence table


### Alerts involving a user  


List 100 alerts involving a certain user.  

```query
let userID = "<inert your AAD user ID>";
let userSid = "<inert your user SID>";
AlertEvidence
| where EntityType == "User" and (AccountObjectId == userID or AccountSid == userSid )
| join AlertInfo on AlertId
| project Timestamp, AlertId, Title, Category , Severity , ServiceSource , DetectionSource , AttackTechniques, AccountObjectId, AccountName, AccountDomain , AccountSid  
| limit 100
```

