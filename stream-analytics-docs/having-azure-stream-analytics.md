---
title: "HAVING (Azure Stream Analytics)"
description: "Specifies a search condition for a group or an aggregate. HAVING can be used only with the SELECT expression."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# HAVING (Azure Stream Analytics)
  Specifies a search condition for a group or an aggregate. HAVING can be used only with the SELECT expression. HAVING is typically used in a GROUP BY clause. When GROUP BY is not used, HAVING behaves like a WHERE clause.  
  
 ## Syntax  
  
```SQL   
[ HAVING <search condition> ]  
```  
  
## Arguments  
 **<search_condition>**  
  
 Specifies the search condition for the group or the aggregate to meet.  
  
## Example  
  
```SQL  
SELECT TollId, System.Timestamp() AS WinEndTime, COUNT(*)   
FROM TollTagEntry TIMESTAMP BY EntryTime  
GROUP BY TumblingWindow( minute , 3 ) , TollId  
HAVING COUNT(*) > 2  
  
```  
  
  
