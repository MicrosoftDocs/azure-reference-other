---
title: CAST (Azure Stream Analytics) | Microsoft Docs
description: Converts an expression of one data type to another within the supported types in Stream Analytics Query Language.
applies_to: 
  - "Azure"
services: stream-analytics
author: jasonwhowell
ms.author: jasonh
manager: kfile
ms.service: stream-analytics
ms.topic: reference
ms.assetid: 1cddcf7a-cdc7-4efc-91c3-9f8058b0e8c7
caps.latest.revision: 8
ms.workload: data-services
ms.date: 05/17/2018
---

# CAST (Azure Stream Analytics)
Converts an expression of one data type to another within the supported types in Stream Analytics Query Language. 

If the conversion cannot be performed, the function fails and causes the job to stop. For example, the clause `CAST ('this is a string' AS bigint)` results in a job failure since the input string cannot be converted into a bigint data type. To avoid type cast failures, use [TRY_CAST](try-cast-azure-stream-analytics.md) instead.
    
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
  
## See also
For more information on Stream Analytics data types, see:
- [Data types](data-types-azure-stream-analytics.md)
- [Complex data types](complex-data-types-stream-analytics.md)
- [TRY_CAST](try-cast-azure-stream-analytics.md)
