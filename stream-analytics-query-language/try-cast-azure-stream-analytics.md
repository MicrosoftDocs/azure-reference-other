---
title: "TRY_CAST (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 94e78203-32fd-44b8-a1bd-47457c30bfb3
caps.latest.revision: 5
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# TRY_CAST (Azure Stream Analytics)
  Returns a value cast to the specified data type if the cast succeeds; otherwise, returns null.  
  
 **Syntax**  
  
```  
TRY_CAST ( expression AS data_type)  
  
```  
  
## Arguments  
 **expression**  
  
 The value to be cast. Any valid expression.  
  
 **data_type**  
  
 The data type into which to cast expression. Is the target data type supported by Stream Analytics Query Language.  
  
## Return Types  
 Returns a value cast to the specified data type if the cast succeeds; otherwise, returns null.  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime   
FROM Input  
WHERE TRY_CAST( EntryTime AS datetime) IS NOT NULL  
```  
  
  