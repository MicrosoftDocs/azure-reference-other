---
title: Example log table queries for ACSEmailStatusUpdateOperational
description:  Example queries for ACSEmailStatusUpdateOperational log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 06/04/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSEmailStatusUpdateOperational table


### Email failed deliveries by recipient ID  


List recipients and failed delivery status.  

```query
ACSEmailStatusUpdateOperational
| where isnotempty(RecipientId)
| where DeliveryStatus != "Delivered"
| limit 100
```



### Email Failed Deliveries by Message Id  


List message ids and failed status.  

```query
ACSEmailStatusUpdateOperational
| where isempty(RecipientId) 
| where DeliveryStatus != "OutForDelivery"
| limit 100
```



### Email Bounced and Suppressed Recipients  


List recipients that have been dropped due to a hard bounce or suppressed due to customer managed opt-outs.  

```query
ACSEmailStatusUpdateOperational
| where DeliveryStatus == "Bounced" or DeliveryStatus == "Suppressed"
| where CorrelationId == "<email-send-request-message-id>"
| limit 100
```

