---
title: "CONCAT (Azure Stream Analytics) | Microsoft Docs"
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
ms.assetid: 57e62210-6923-4306-918c-6e0e8834afb0
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: sngun
---
# CONCAT (Azure Stream Analytics)
  Returns a string that is the result of concatenating two or more string values.  
  
 **Syntax**  
  
```SQL  
CONCAT ( string_value1, string_value2 [, string_valueN ] )  
```  
  
## Arguments  
 **string_value**  
  
 A string value to concatenate to the other values.  
  
## Return Types  
 nvarchar(max)  
  
## Examples  
  
```SQL 
SELECT TollId, EntryTime, CONCAT ( 'Make:', Make, ' And Model:', Model) AS MakeModel, LicensePlate  
FROM Input TIMESTAMP BY EntryTime  
WHERE Toll > 5  
  
```  
  
  