---
title: "TopOne (Azure Stream Analytics)"
description: "Returns the top-rank record, where rank defines the ranking position of the event in the window according to the specified ordering."
applies_to: 
  - "Azure"
ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# TopOne (Azure Stream Analytics)
  Returns the top-rank record, where rank defines the ranking position of the event in the window according to the specified ordering. Ordering/ranking is based on event columns and can be specified in ORDER BY clause.  
  
 ## Syntax  
  
```SQL
-- Aggregate Function Syntax
TopOne( [ <scalar_expression> ] ) OVER (ORDER BY (<column name> [ASC |DESC])+)  

-- Analytic Function Syntax
TopOne( [ <scalar_expression> ] ) OVER ([<PARTITION BY clause>] ORDER BY (<column name> [ASC |DESC])+ <LIMIT DURATION clause> [<WHEN clause>])  

```
  
## Arguments

**\<scalar_expression>**

 TopOne takes an optional scalar expression that allows you to specify a projection over the top event. Without the parameter, full event record is returned.

 **\<column_name>**  
  
 Specifies the name of the column in the input event by which ordering will be done. Note that only ordering by bigint, float and datetime types are allowed.  

**OVER ([\<PARTITION BY clause> \<LIMIT DURATION clause> [\<WHEN clause>]]**

 Determines the group of rows over which TopOne is applied. The PARTITION BY clause specifies that the rows with the same partition key will be grouped together. The LIMIT DURATION clause specifies how much history is included in the group. The optional WHEN clause specifies a boolean condition for the rows to be included in the group. See [OVER clause](over-azure-stream-analytics.md) for more details on the usage.

## Return Types

 Value projected by the `<scalar_expression>` parameter, or a record value if no parameter is provided.  

## Examples  
  
```SQL  
SELECT   
    TopOne() OVER (ORDER BY value DESC) as topEvent  
FROM input  
GROUP BY Tumbling(second, 10)  
  
```  
  
```SQL  
SELECT   
    TopOne(x * y) OVER (ORDER BY value DESC) as topEvent  
FROM input  
GROUP BY Tumbling(second, 10)  
  
```  
  
