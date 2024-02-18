---
title: Example log table queries for LASummaryLogs
description:  Example queries for LASummaryLogs log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 02/18/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the LASummaryLogs table


### Bin Rules Query Duration  


Get a list of bin rules with their query duration.  

```query
LASummaryLogs
| summarize QueryDurationInSeconds = sum(QueryDurationMs)/1000 by RuleName, BinStartTime
| sort by QueryDurationInSeconds desc
```

