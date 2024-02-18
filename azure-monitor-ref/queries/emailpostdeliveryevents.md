---
title: Example log table queries for EmailPostDeliveryEvents
description:  Example queries for EmailPostDeliveryEvents log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the EmailPostDeliveryEvents table


### Post-delivery administrator actions  


Display post-delivery actions made by Administrator.  

```query
EmailPostDeliveryEvents
| where ActionTrigger == 'AdminAction'
| take 100 
```



### Unremediated post-delivery phishing email detections  


Display post-delivery phishing email detections which was not remediated.  

```query
EmailPostDeliveryEvents
| where ActionType == 'Phish ZAP' and ActionResult == 'Error'
| join EmailEvents on NetworkMessageId, RecipientEmailAddress  
| take 100
```



### Full email processing details  


Emails that include predefined post-delivery actions or automatic rules, by sender and subject.  

```query
let mySender = "<insert sender email address>";
let subject = "<insert email subject>";
EmailEvents
| where SenderFromAddress == mySender and Subject == subject
| join EmailPostDeliveryEvents on NetworkMessageId, RecipientEmailAddress 
| take 100
```

