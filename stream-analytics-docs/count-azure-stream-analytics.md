---
title: "COUNT"
description: "Returns the number of items in a group. COUNT always returns a bigint data type value."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# COUNT
:white_check_mark: Azure Stream Analytics :white_check_mark: Fabric Eventstream

Returns the number of items in a group. COUNT always returns a bigint data type value.  
  
 ## Syntax  
  
```SQL
-- Aggregate Function Syntax
COUNT ( { [ [ALL | DISTINCT] expression ] | * } ) 

-- Analytic Function Syntax
COUNT ( { [expression] | * }) OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])
  
```  
  
## Arguments  
**ALL**

Applies the aggregate function to all values. ALL is the default.

**DISTINCT**

Specifies that COUNT returns the number of unique non-null values.

**expression**  
  
Is an expression of any type or a column name. Aggregate functions and sub queries are not permitted.  
  
\* (wildcard expression) 
  
Specifies that all events should be counted to return the total number of events in a group. COUNT(\*) takes no parameters. COUNT(\*) does not require an expression parameter because, by definition, it does not use information about any particular column. COUNT(\*) returns the number of events without getting rid of duplicates. It counts each event separately. This includes events that contain null values, returning a 0 for null values.

**OVER ([\<PARTITION BY clause> \<LIMIT DURATION clause> [\<WHEN clause>]]**

Determines the group of rows over which COUNT is applied. The PARTITION BY clause specifies that the rows with the same partition key will be grouped together. The LIMIT DURATION clause specifies how much history is included in the group. The WHEN clause specifies a boolean condition for the rows to be included in the group. See [OVER clause](over-azure-stream-analytics.md) for more details on the usage.

## Remarks

 - COUNT(*) returns the number of events including NULL values and duplicates.

 - COUNT(ALL expression) and COUNT(expression) evaluates expression for each event in a group and returns the number of non-null values.

 - COUNT(DISTINCT expression) evaluates expression for each event in a group and returns the number of unique, non-null values.

 - COUNT(input_stream) is equivalent to COUNT() and COUNT(*), but COUNT(DISTINCT input_stream) counts only unique events.

 - COUNT(DISTINCT expression) is not supported as an analytic function. That is, you can not use COUNT(DISTINCT expression) with the OVER clause.

  
## Return Types  
 bigint  
  
## Examples  

```SQL  
SELECT System.Timestamp() AS OutTime, TollId, COUNT(*)   
FROM Input TIMESTAMP BY EntryTime  
GROUP BY TollId, TumblingWindow(minute,3)  
```  

## See Also
[GROUP BY clause](group-by-azure-stream-analytics.md)   
[OVER clause](over-azure-stream-analytics.md)
