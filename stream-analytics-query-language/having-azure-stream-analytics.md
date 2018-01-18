---
title: "HAVING (Azure Stream Analytics) | Microsoft Docs"
description: "Specifies a search condition for a group or an aggregate. HAVING can be used only with the SELECT expression."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: a5f2e124-86a0-4163-a125-3a0c9e4cc615
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# HAVING (Azure Stream Analytics)
  Specifies a search condition for a group or an aggregate. HAVING can be used only with the SELECT expression. HAVING is typically used in a GROUP BY clause. When GROUP BY is not used, HAVING behaves like a WHERE clause.  
  
 **Syntax**  
  
```  
[ HAVING <search condition> ]  
```  
  
## Arguments  
 **<search_condition>**  
  
 Specifies the search condition for the group or the aggregate to meet.  
  
## Example  
  
```SQL  
SELECT TollId, System.Timestamp AS WinEndTime, COUNT(*)   
FROM TollTagEntry TIMESTAMP BY EntryTime  
GROUP BY TumblingWindow( minute , 3 ) , TollId  
HAVING COUNT(*) > 2  
  
```  
  
  