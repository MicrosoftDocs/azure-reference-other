---
title: "YEAR (Azure Stream Analytics) | Microsoft Docs"
description: "Returns an integer that represents the year of the specified date."
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: b4015fdf-9d76-4688-b326-216493adcb47
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# YEAR (Azure Stream Analytics)
  Returns an integer that represents the year of the specified date  
  
 **Syntax**  
  
```  
YEAR ( date )  
```  
  
## Arguments  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT YEAR (EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  