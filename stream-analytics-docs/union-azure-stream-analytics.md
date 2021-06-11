---
title: "UNION (Azure Stream Analytics)"
description: "Combines the results of two or more queries into a single result set that includes all the rows that belong to all queries in the union."
applies_to: 
  - "Azure"


ms.service: stream-analytics
ms.topic: reference
ms.date: 04/22/2016
---
# UNION (Azure Stream Analytics)
  Combines the results of two or more queries into a single result set that includes all the rows that belong to all queries in the union. The UNION operation is different from using joins that combine columns from two tables.  
  
 The following are basic rules for combining the result sets of two queries by using UNION:  
  
-   The number and the order of the columns must be the same in all queries.  
-   The data types must be compatible.
-   Streams must have the same partition and partition count
  
 ## Syntax  
  
```SQL   
  { <query_specification> | ( <query_expression> ) }   
  UNION  
  <query_specification | ( <query_expression> )   
 [ UNION <query_specification> | ( <query_expression> )   
    [ ...n ] ]  
  
```  
  
## Arguments  
 **<query_specification> | ( <query_expression> )**  
  
 Is a query specification or query expression that returns data to be combined with the data from another query specification or query expression. The definitions of the columns that are part of a UNION operation have to be the same or must be named same using an alias and must be compatible.  
  
 **UNION**  
  
 Specifies that multiple result sets are to be combined and returned as a single result set. UNION incorporates all rows into the results. This includes duplicates.  
  
## Example  
  
```SQL  
SELECT TollId, EntryTime AS Time, LicensePlate   
FROM Input1 TIMESTAMP BY EntryTime   
UNION  
SELECT TollId, ExitTime AS Time, LicensePlate   
FROM Input2 TIMESTAMP BY ExitTime  
  
```  
If need be, streams can be [repartitioned](../stream-analytics/repartition) to match (either in the same job as below, or another one to achieve better performance):

```SQL
WITH Input1_P as (
SELECT * FROM Input1 PARTITION BY partitionId INTO 2
),

Input2_P as (
SELET * FROM Input2 PARTITION BY partitionId INTO 2
)

SELECT TollId, EntryTime AS Time, LicensePlate   
FROM Input1_P TIMESTAMP BY EntryTime
UNION  
SELECT TollId, ExitTime AS Time, LicensePlate   
FROM Input2_P TIMESTAMP BY ExitTime
```
  
