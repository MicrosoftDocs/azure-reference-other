---
title: Example log table queries for ACSEmailStatusUpdateOperational
description:  Example queries for ACSEmailStatusUpdateOperational log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

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

