---
title: Example log table queries for AWSCloudTrail
description:  Example queries for AWSCloudTrail log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AWSCloudTrail table


### New users per region  


Returns count of created users per region.  

```query
AWSCloudTrail
| where EventName == "CreateUser"
| summarize count() by AWSRegion
```



### All AWS CloudTrail events  


Lists all AWS cloud trail events.  

```query
AWSCloudTrail
| project TimeGenerated, EventName, EventTypeName, UserIdentityAccountId, UserIdentityPrincipalid, UserAgent, UserIdentityUserName, SessionMfaAuthenticated, SourceIpAddress, AWSRegion, EventSource, AdditionalEventData, ResponseElements, SessionIssuerUserName
```



### AWSCT for user  


AWS activity for a user.  

```query
// Set v_sessionissuerusername and v_userpid  with the details of the user of interest
let v_sessionissuerusername ="abc";let v_userpid ="AIDxXxXxXxXxXxX";
AWSCloudTrail
| where SessionIssuerUserName == v_sessionissuerusername  or UserIdentityPrincipalid ==v_userpid
| project TimeGenerated, EventName, EventTypeName, UserIdentityAccountId, UserIdentityPrincipalid, UserAgent,     UserIdentityUserName, SessionMfaAuthenticated, SourceIpAddress, AWSRegion, EventSource, AdditionalEventData, ResponseElements, SessionIssuerUserName
```



### AWS console sign in  


Lists AWS signin events.  

```query
AWSCloudTrail
| where EventName =~ "ConsoleLogin"
| extend MFAUsed = tostring(parse_json(AdditionalEventData).MFAUsed), LoginResult = tostring(parse_json(ResponseElements).ConsoleLogin)
| summarize Count=count() by UserIdentityAccountId, UserIdentityUserName, MFAUsed, LoginResult
```

