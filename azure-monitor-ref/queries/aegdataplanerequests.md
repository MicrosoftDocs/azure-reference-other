---
title: Example log table queries for AegDataPlaneRequests
description:  Example queries for AegDataPlaneRequests log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the AegDataPlaneRequests table


### Unique unauthorized or forbidden client IP addresses  


Get a list of client IP addresses from which EventGrid received unauthorized or forbidden requests.  

```query
EventGridDataPlaneRequests
| where OperationResult == "Unauthorized" or OperationResult == "Forbidden"
| summarize count() by ClientIpAddress
```

