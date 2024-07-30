---
title: Example log table queries for ACSEmailSendMailOperational
description:  Example queries for ACSEmailSendMailOperational log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the ACSEmailSendMailOperational table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Email Send Request Summary  


Summary of send mail requests.  

```query
ACSEmailSendMailOperational
| summarize TotalMessageCount = dcount(CorrelationId),
            TotalSize = sum(Size),
            AvgSizePerMessage = avg(Size),
            AvgRecipientsPerMessage = avg(UniqueRecipientsCount),
            AvgAttachmentsPerMessage = avg(AttachmentsCount),
            SizeAvg = avg(Size) 
```

