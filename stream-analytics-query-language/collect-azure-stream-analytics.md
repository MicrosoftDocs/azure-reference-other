---
title: "Collect (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-05-24"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 4ecadc16-b061-45ff-935f-3d03996a53f5
caps.latest.revision: 7
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# Collect (Azure Stream Analytics)
Returns an array with all record values  from the window.

 
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
  
```  
SELECT Collect() AS allEvents 
FROM Input 
GROUP BY TumblingWindow(second,10) 
