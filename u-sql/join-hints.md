---
title: "Join Hints | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 30e67e1c-20b5-4ac0-947b-70e4da0da83f
caps.latest.revision: 3
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Join Hints
In addition to the JOIN operators, U-SQL optionally allows the query author to provide hints on the type of join to choose and what parallel join execution to use.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Join_Hints :=                                                                                            
     [Parallel_Join_Hint] [Join_Algorithm_Hint].<br />
Parallel_Join_Hint :=  
     'SERIAL' | 'PAIR' | 'BROADCASTLEFT' | 'BROADCASTRIGHT' | 'FULLCROSS'.<br />
Join_Algorithm_Hint :=  
     'MERGE' | 'HASH' | 'LOOP' | 'INDEXLOOKUP'.
</pre></td></tr></table>
  
These hints impact the plan generation of the query optimizer. If the optimizer cannot find a succession of optimizer rules to satisfy the requested hints, for example because the hints are not applicable to a specific JOIN, a NO PLAN error will be raised.  
  
These hints are best used with care, since specifying a certain hint will make it impossible for the optimizer to find a better plan. They should only be used if the default plan is not optimal.  

### See Also 
* [U-SQL SELECT Selecting from Joins](u-sql-select-selecting-from-joins.md)  
