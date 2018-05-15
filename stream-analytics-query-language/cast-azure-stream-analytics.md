---
title: "CAST (Azure Stream Analytics) | Microsoft Docs"
description: "Converts an expression of one data type to another within the supported types in Stream Analytics Query Language."
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 1cddcf7a-cdc7-4efc-91c3-9f8058b0e8c7
caps.latest.revision: 8
ms.workload: data-services
ms.date: 07/19/2017
ms.author: jasonh
---

# CAST (Azure Stream Analytics)
  Converts an expression of one data type to another within the supported types in Stream Analytics Query Language. This will fail and cause the job to stop if the conversion cannot be performed.
  
  For example, CAST ('this is a string' AS bigint) will result in a job failure. When this is not a desired outcome use [TRY_CAST &#40;Azure Stream Analytics&#41;](try-cast-azure-stream-analytics.md) instead.
    
  
 **Syntax**  
  
``` 
CAST ( expression AS data_type)  
  
```  
  
## Arguments  
 **expression**  
  
 Is any valid expression.  
  
 **data_type**  
  
 Is the target data type supported by Stream Analytics Query Language.  
  
## Return Types  
 Returns expression translated to data_type.  
  
## Examples  
  
```SQL  
  
SELECT TollId, EntryTime, LicensePlate, State, Make   
FROM Input TIMESTAMP BY EntryTime  
WHERE CAST( TollId AS bigint) > 2  
  
```  
  
  
