---
title: "GetArrayElements (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: d1bd88f0-9c16-4a43-80dd-5cb54d8bd530
caps.latest.revision: 8
ms.workload: data-services
ms.date: 22/04/2016
ms.author: sngun
---
# GetArrayElements (Azure Stream Analytics)
  Returns a dataset with array values and indexes. The result of the GetArrayElements function must be used with [CROSS APPLY](apply-azure-stream-analytics.md) operator only.  
  
 **Syntax**  
  
```  
GetArrayElements ( column_reference )  
```  
  
## Arguments  
 **column_reference**  
  
 Is the column reference expression to be evaluated. Column must be of type Array.  
  
## Return Types  
 Returns a dataset with ArrayIndex and ArrayValue columns.  
  
## Examples  
  
```SQL  
SELECT   
    arrayElement.ArrayIndex,  
    arrayElement.ArrayValue  
FROM input as event  
CROSS APPLY GetArrayElements(event.arrayField) AS arrayElement  
  
```  
  
  