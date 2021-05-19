---
title: TRY_CAST (Azure Stream Analytics)
description: Returns a value cast to the specified data type if the cast succeeds; otherwise, returns null.
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 04/22/2016
---
# TRY_CAST (Azure Stream Analytics)
Returns a value cast to the specified data type if the cast succeeds; otherwise, returns NULL. Supports the [data types](data-types-azure-stream-analytics.md) in the Stream Analytics Query Language.

For example, the clause `TRY_CAST ('this is a string' AS bigint)` results in a NULL since the input string cannot be converted into the `bigint` data type. If you need the cast to fail when there is an incompatible data type, use [CAST](cast-azure-stream-analytics.md) function instead.

This function is useful to help ensure data purity, by enforcing the data types on an input column. You can filter out dirty data that does not match the expected data type in a given column by using TRY_CAST on each column. 

 ## Syntax  
  
```SQL   
TRY_CAST ( expression AS data_type)  
  
```  
  
## Arguments  
 **expression**  
  
 The value to be cast. Any valid expression.  
  
 **data_type**  
 The data type into which to cast expression. Use a [data type](data-types-azure-stream-analytics.md) supported by the Stream Analytics Query Language.  
  
## Return Types  
 Returns a value cast to the specified data type if the cast succeeds; otherwise, returns null.  
  
## Examples  
To filter out potentially bad datetime values in the EntryTime column, use TRY_CAST for the column, and use the IS NOT NULL comparison, since NULL values indicate the cast attempt has failed.

```SQL  
SELECT TollId, EntryTime   
FROM Input  
WHERE TRY_CAST(EntryTime AS datetime) IS NOT NULL  
```  
  
## See also
For more information on Stream Analytics data types, see:
- [Data types](data-types-azure-stream-analytics.md)
- [CAST](cast-azure-stream-analytics.md)
- [Parsing JSON and AVRO data](/azure/stream-analytics/stream-analytics-parsing-json)
