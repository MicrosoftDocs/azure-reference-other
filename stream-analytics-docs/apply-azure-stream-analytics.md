---
title: "APPLY (Azure Stream Analytics)"
description: "The APPLY operator allows you to invoke a table-valued function for each row returned by an outer table expression of a query."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---

# APPLY (Azure Stream Analytics)
  The APPLY operator allows you to invoke a table-valued function for each row returned by an outer table expression of a query. The table-valued function acts as the right input and the outer table expression acts as the left input. The right input is evaluated for each row from the left input and the rows produced are combined for the final output. The list of columns produced by the APPLY operator is the set of columns in the left input followed by the list of columns returned by the right input.  
  
 There are two forms of APPLY: CROSS APPLY and OUTER APPLY. 
 
CROSS APPLY returns only rows from the outer table that produce a result set from the table-valued function. The result of a CROSS APPLY cannot be used as the target value of the [TIMESTAMP BY](timestamp-by-azure-stream-analytics.md). However, you can use one Azure Stream Analytics job that performs the CROSS APPLY, and use a second job to perform the TIMESTAMP BY.

OUTER APPLY returns both rows that produce a result set, and rows that do not, with NULL values in the columns produced by the table-valued function.  
  
 There are two table-valued functions available in Azure Stream Analytics to facilitate working with Array and Record type fields. They are [GetArrayElements](getarrayelements-azure-stream-analytics.md) and [GetRecordProperties](getrecordproperties-azure-stream-analytics.md).  
  
 ## Syntax  
  
```SQL
  
<input> {CROSS | OUTER} APPLY <elements_selector>  
  
<input> ::= input_name |  input_alias  
  
<elements_selector> ::=   
{GetArrayElements | GetRecordProperties} (<column_name>) AS element_name  
  
```  
  
## Arguments  
 **input_name | input_alias**  
  
 The name or alias of the input stream.  
  
 **column_name**  
  
 The name of a column of the input stream.  
  
 **element_name**  
  
 The name of the new column containing the result of the table-valued function.  
  
## Return Types  
 The output is a record containing the initial payload and a record '*element_name*', which contains the result of the table-valued function.  
  
 For the GetArrayElements function the result will be a record with two fields:  
  
-   **ArrayIndex**: the index of the element in the array  
  
-   **ArrayValue**: the value of the element in the array.  
  
 For the GetRecordProperties function the result will be a record with two fields:  
  
-   **PropertyName**: the name of the property in the record.  
  
-   **PropertyValue**: the value of the property in the record.  
  
## Examples  
 In this example, extending the tollbooth scenario, we assume that cars can have more than one license plate (e.g. a car towing a trailer would have two). Cross/outer apply can be used to flatten this array, i.e. get one row per license plate.  
  
```SQL
CREATE TABLE input(TollId nvarchar(max), EntryTime datetime, Licenses array)  
  
SELECT e.TollId, e.EntryTime, flat.ArrayValue AS licensePlate   
   FROM input AS e   
   CROSS APPLY GetArrayElements(e.Licenses) AS flat  
  
```  
  
 The query can be modified to use outer apply in order to also keep track of cars without any license plate.  
  
```SQL
SELECT e.TollId, e.EntryTime,   
flat.ArrayValue AS licensePlate, flat.ArrayIndex AS licensePlateIndex  
   FROM input AS e   
   OUTER APPLY GetArrayElements(e.Licenses) AS flat  
  
```  
  
 Another example using nested arrays (array of arrays).  
  
```SQL
WITH firstQuery AS (  
   SELECT input.TollId, input.EntryTime,   
   flat.ArrayIndex AS i1, flat.ArrayValue AS licenses   
      FROM input   
      CROSS APPLY GetArrayElements(input.ArrayOfArray) AS flat)  
  
SELECT firstQuery.TollId, firstQuery.EntryTime, firstQuery.i1,   
flat2.ArrayIndex AS i2, flat2.ArrayValue AS license  
   FROM firstQuery  
   CROSS APPLY GetArrayElements(firstQuery.licenses) AS flat2  
  
```  
  
  
