---
title: "LEN (Azure Stream Analytics) | Microsoft Docs"
description: "Returns the number of characters of the specified string expression, excluding trailing blanks."
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 82f25a01-f71c-470a-9b01-93fc374fda90
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: jasonh
---
# LEN (Azure Stream Analytics)
  Returns the number of characters of the specified string expression, excluding trailing blanks.  
  
 **Syntax**  
  
```  
LEN ( string_expression )  
  
```  
  
## Arguments  
 **string_expression**  
  
 Is the string expression to be evaluated. string_expression can be a constant or column of type nvarchar(max)  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime, LicensePlate, LEN (LicensePlate) AS Len_License  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
```  
  
  
