---
title: "Collect (Azure Stream Analytics) | Microsoft Docs"
description: "Returns an array with all record values from the window. "
applies_to: 
  - "Azure"
services: "stream-analytics"
author: SnehaGunda
manager: kfile

ms.service: stream-analytics
ms.suite: ""
ms.topic: reference
ms.tgt_pltfrm: ""   
ms.assetid: 4ecadc16-b061-45ff-935f-3d03996a53f5
caps.latest.revision: 7
ms.workload: data-services
ms.date: 24/05/2016
ms.author: sngun
---

# Collect (Azure Stream Analytics)
Returns an array with all record values from the window.

 
 **Syntax**  
  
```  
Collect()
```  
  
## Arguments  
Collect does not take any arguments.
  
## Return Types  
Array of record values.  

## General Remarks
Ordering of the values within returned array is **not** guaranteed

## Examples  
  
```SQL  
SELECT Collect() AS allEvents 
FROM Input 
GROUP BY TumblingWindow(second,10) 
