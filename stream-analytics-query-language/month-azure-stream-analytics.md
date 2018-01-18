---
title: "MONTH (Azure Stream Analytics) | Microsoft Docs"
description: ""
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 599fb307-c1ae-465d-835c-d7d1ea9455c2
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# MONTH (Azure Stream Analytics)
  Returns an integer that represents the month of the specified date.  
  
 **Syntax**  
  
```  
MONTH ( date )  
```  
  
## Arguments  
 **date**  
  
 Is an expression that can be resolved to a datetime. date can be an expression, column expression, or string literal.  
  
## Return Types  
 bigint  
  
## Examples  
  
```SQL  
SELECT MONTH (EntryTime)  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  