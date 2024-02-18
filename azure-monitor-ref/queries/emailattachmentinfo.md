---
title: Example log table queries for EmailAttachmentInfo
description:  Example queries for EmailAttachmentInfo log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EmailAttachmentInfo table


### Files from malicious sender  


Finds the first appearance of files sent by a malicious sender in your organization at selected time frame. To see earlier appearances please increase selected time range.  

```query
let MaliciousSender = "<insert the sender email address>";
EmailAttachmentInfo
| where SenderFromAddress =~ MaliciousSender
| project SHA256 = tolower(SHA256)
| join (
DeviceFileEvents
) on SHA256
| summarize FirstAppearance = min(Timestamp) by DeviceName, SHA256, FileName 
| take 100
```



### Emails to external domains with attachments  


Emails sent to an external domain that include attachments.  

```query
EmailEvents
| where EmailDirection == "Outbound" and AttachmentCount > 0
| join EmailAttachmentInfo on NetworkMessageId 
| project Timestamp, Subject, SenderFromAddress, RecipientEmailAddress, NetworkMessageId, FileName, AttachmentCount 
| take 1000
```

