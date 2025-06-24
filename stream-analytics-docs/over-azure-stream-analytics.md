---
title: "OVER"
description: "Defines the grouping of rows before an associated aggregate or analytic function is applied."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# OVER
For each row, the OVER clause determines the grouping of rows before an associated aggregate or analytic function is applied. 
  
You can use the OVER clause anywhere a scalar function is allowed. For example, you can use the OVER clause in the SELECT, WHERE, JOIN or GROUP BY clauses.

The OVER clause groups rows directly from the query input. It is not affected by predicates in the WHERE clause, join conditions in the JOIN clause, or grouping conditions in the GROUP BY clause.

Currently, the following aggregate functions are supported with the OVER clause:
* SUM
* AVG
* MIN
* MAX
  
## Syntax  
  
```SQL
OVER ([<PARTITION BY clause>] <LIMIT DURATION clause> [<WHEN clause>])

<PARTITION BY clause> ::== PARTITION BY partition_key, ... [n]

<LIMIT DURATION clause> ::== LIMIT DURATION (unit, length)

<WHEN clause> ::== WHEN boolean_expression
```  
  
## Arguments  
 **\<PARTITION BY clause>**  

Specifies that only the rows with the same \<partition_key> will be considered for the aggregate or analytic function.
  
 **\<LIMIT DURATION clause>**  
  
Specifies how much history from the current row is included in the group. See [DATEDIFF](datediff-azure-stream-analytics.md) for a detailed description of supported units and their abbreviations.

**\<WHEN CLAUSE>**

Specifies the boolean condition for the rows to be included in the group.
  
## General Remarks  

Applying an aggregate or analytic function with OVER on the result set of a [windowing function](windowing-azure-stream-analytics.md) may produce unexpected results. Windowing functions alter the timestamp of events, as every window operation outputs event at the end of the window. The current timestamp of an event can be accessed with [system.timestamp()](system-timestamp-stream-analytics.md), after a window operation it will differ from the original event time attribute.

## Examples

Compute the average temperature over the last 5 minutes, per sensor:

```SQL  
SELECT AVG(temperature) OVER (PARTITION BY id LIMIT DURATION (minute, 5))
FROM input
```  

Throw an alert if resource has been unhealthy over the last hour:

```SQL
SELECT 1 AS alert
FROM input
WHERE MAX(healthy) OVER (PARTITION BY id LIMIT DURATION (hour, 1)) = 0
```

## See Also  
[Analytic Functions](analytic-functions-azure-stream-analytics.md)   
[Aggregate Functions](aggregate-functions-azure-stream-analytics.md)  
