---
title: "CollectTOP (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-07-06"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 88431761-5ccc-4225-b9d0-d54811c6393e
caps.latest.revision: 10
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# CollectTOP (Azure Stream Analytics)
  Returns an array of ranked records, where rank defines the ranking position of the event in the window according to the specified ordering. Ordering/ranking is based on event columns and can be specified in ORDER BY clause.  
  
 **Syntax**  
  
```  
CollectTop(<number of events as integer literal>) OVER (ORDER BY (<column name> [ASC |DESC])+)  
```  
  
## Arguments  
 **\<number of events as integer literal>**  
  
 The number of top events the user wants to collect from the window.  
  
 **\<column name>**  
  
 Name of the column in the input event, by which ordering will be done. Only ordering by bigint/float/datetime types is allowed.  
  
## Return Types  
 Array of records of type { “rank” : bigint, “value”: record  }  
  
## Remarks  
 Null is treated as the minimal value, for more information look at [https://msdn.microsoft.com/library/ms188385.aspx](https://msdn.microsoft.com/library/ms188385.aspx)  
  
## Examples  
  
```  
SELECT   
    value1,  
    CollectTop(2) OVER (ORDER BY value2 ASC, value3 DESC) as top1  
FROM testinput timestamp by time  
GROUP BY TumblingWindow(second, 5), value1  
```  
  
 Example input:  
  
![SA-COLLECTTOP-INPUTv2.PNG](media/sa-collecttop-inputv2.png)
  
 Example output:  

![SA-COLLECTTOP-OUTPUT.PNG](media/sa-collecttop-output.png)

  