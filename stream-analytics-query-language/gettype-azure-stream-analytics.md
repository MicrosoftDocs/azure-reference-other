---
title: "GetType (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 94c6d620-c00f-4246-86b3-cd4e2c040a61
caps.latest.revision: 4
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# GetType (Azure Stream Analytics)
  Returns a data type name of the value.  
  
 **Syntax**  
  
```  
GetType (expression)  
  
```  
  
## Arguments  
 **expression**  
  
 Is any valid expression.  
  
## Return Types  
 Returns a data type name for the expression. Please see all supported data types in [Data Types &#40;Azure Stream Analytics&#41;](data-types-azure-stream-analytics.md).  
  
## Examples  
  
```SQL  
SELECT TollId, EntryTime   
FROM Input  
WHERE GetType( EntryTime ) = ‘datetime’  
```  
  
  