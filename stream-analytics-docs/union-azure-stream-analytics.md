---
title: "UNION (Azure Stream Analytics) | Microsoft Docs"
description: "Combines the results of two or more queries into a single result set that includes all the rows that belong to all queries in the union."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 4642814a-14d1-4331-bb87-e5865cd9ae1f
caps.latest.revision: 7
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# UNION (Azure Stream Analytics)
  Combines the results of two or more queries into a single result set that includes all the rows that belong to all queries in the union. The UNION operation is different from using joins that combine columns from two tables.  
  
 The following are basic rules for combining the result sets of two queries by using UNION:  
  
-   The number and the order of the columns must be the same in all queries.  
  
-   The data types must be compatible.  
  
 ## Syntax  
  
```  
  { <query_specification> | ( <query_expression> ) }   
  UNION  
  <query_specification | ( <query_expression> )   
 [ UNION <query_specification> | ( <query_expression> )   
    [ ...n ] ]  
  
```  
  
## Arguments  
 **<query_specification> | ( <query_expression> )**  
  
 Is a query specification or query expression that returns data to be combined with the data from another query specification or query expression. The definitions of the columns that are part of a UNION operation have to be the same or must be named same using an alias and must be compatible.  
  
 **UNION**  
  
 Specifies that multiple result sets are to be combined and returned as a single result set. UNION incorporates all rows into the results. This includes duplicates.  
  
## Example  
  
```SQL  
SELECT TollId, EntryTime AS Time, LicensePlate   
FROM Input1 TIMESTAMP BY EntryTime   
UNION  
SELECT TollId, ExitTime AS Time, LicensePlate   
FROM Input2 TIMESTAMP BY ExitTime  
  
```  
  
  
