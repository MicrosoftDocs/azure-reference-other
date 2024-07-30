---
title: Example log table queries for Watchlist
description:  Example queries for Watchlist log table
ms.topic: reference
ms.service: azure-monitor
ms.author: edbaynash
author: EdB-MSFT
ms.date: 07/30/2024

# NOTE:  This content is automatically generated using API calls to Azure. Any edits made on these files will be overwritten in the next run of the script. 

---

# Queries for the Watchlist table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Get Watchlist aliases  


Gets a distinct list of all Watchlist aliases in a workspace.  

```query
Watchlist
| where _DTItemType == "Watchlist"
| where _DTTimestamp > ago(5d)
| distinct WatchlistAlias
```



### Lookup events using a Watchlist  


Lookup events in Heartbeat table against data from a Watchlist by treating the Watchlist as a table for joins and lookups.  

```query
Heartbeat
| lookup kind=leftouter _GetWatchlist('mywatchlist')
 on $left.ComputerIP == $right.SearchKey
 | limit 100
```

