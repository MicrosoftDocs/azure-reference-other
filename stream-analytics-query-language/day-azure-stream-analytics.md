---
title: "DAY (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: 0ffa3e9c-6bf4-4d46-ad0b-228d6125c5c5
caps.latest.revision: 6
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# DAY (Azure Stream Analytics)
  Returns an integer representing the day (day of the month) of the specified date.  
  
 **Syntax**  
  
```  
DAY ( date )  
```  
  
## Arguments  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 bigint  
  
## Examples  
  
```  
SELECT DAY (EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  