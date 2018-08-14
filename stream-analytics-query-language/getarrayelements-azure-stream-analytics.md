---
title: GetArrayElements (Azure Stream Analytics) | Microsoft Docs
description: Returns a dataset with array values and indexes. Useful for parsing arrays and nested objects in JSON and AVRO data.
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
ms.author: mamccrea
manager: kfile
ms.service: stream-analytics
ms.topic: reference
ms.assetid: d1bd88f0-9c16-4a43-80dd-5cb54d8bd530
caps.latest.revision: 8
ms.workload: data-services
ms.date: 05/17/2018
---
# GetArrayElements (Azure Stream Analytics)
Returns a dataset with array values and indexes. The result of the GetArrayElements function must be used with [CROSS APPLY](apply-azure-stream-analytics.md) operator only.  This function is useful for parsing arrays and nested objects in JSON and AVRO formatted input event data. For more examples, see [Parsing JSON and AVRO data](http://docs.microsoft.com/azure/stream-analytics/stream-analytics-parsing-json).
  
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

## See also
- [GetArrayElement](getarrayelement-azure-stream-analytics.md)
- [CROSS APPLY](apply-azure-stream-analytics.md)
- [Parsing JSON and AVRO data](http://docs.microsoft.com/azure/stream-analytics/stream-analytics-parsing-json)
