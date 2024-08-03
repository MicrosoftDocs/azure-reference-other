---
title: "FROM (Azure Stream Analytics)"
description: "Specifies the input stream or a step name associated in a WITH clause. The FROM clause is always required for any SELECT statement."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# FROM (Azure Stream Analytics)
  Specifies the input stream or a step name associated in a WITH clause. The FROM clause is always required for any SELECT statement.  
  
 ## Syntax  
  
```syntaxsql
FROM <input_source> [<PARTITION BY clause>] [<TIMESTAMP BY clause>]
  
<PARTITION BY clause> ::== PARTITION BY <key_spec>

<TIMESTAMP BY clause> ::== TIMESTAMP BY scalar_expression [OVER <key_spec>]

<input_source> ::=   
    {   
      *   
      | { input_name |  input_alias }.*   
      | {  
          [ { input_name | input_alias }. ]  
               { column_name }  
     | expression [ [ AS ] column_alias ]  
         }  
      | column_alias = expression   
    }

<key_spec> ::== { column_name | expression } [,... n]
```  
  
## Arguments  
 **\***  
  
 Specifies that all columns from all input streams in the FROM clause should be returned. The columns are returned by input source, as specified in the FROM clause, and in the order in which they exist in the incoming stream.  
  
 **input_name | input_alias.\***  
  
 Limits the scope of the * to the specified input name.  
  
 **column_name**  
  
 Is the name of a column to return. Qualify column_name to prevent an ambiguous reference, such as occurs when two input source in the FROM clause have columns with duplicate names.  
  
 **expression**  
  
 Is a constant, function, any combination of column names, constants, and functions connected by an operator or operators, or a subquery.  
  
 **Column_alias**  
  
 Is an alternative name to replace the column name in the query result set. For example, an alias such as Quantity, or Quantity to Date, or Qty can be specified for a column named quantity. Aliases are used also to specify names for the results of expressions. column_alias cannot be used in a WHERE, GROUP BY, or HAVING clause.

 **PARTITON BY \<key_spec>**

 Partitions data into subsets based on *\<key_spec>*. This allows the job to consume and write different partitions in parallel. For more information, see [Leverage query parallelization in Azure Stream Analytics](/azure/stream-analytics/stream-analytics-parallelization).

  
 **TIMESTAMP BY scalar_expression [OVER \<key_spec>]**

 Allows events to be timestamped by *scalar_expression* instead of arrival time. The OVER clause can be used to create independent timelines for each distinct key. For more information, see the documentation on [TIMESTAMP BY](timestamp-by-azure-stream-analytics.md).

## Example  
  
```SQL  
SELECT TollId, EntryTime AS VehicleEntryTime, LicensePlate, State, Make, Model, VehicleType, VehicleWeight, Toll, Tag   
FROM TollTagEntry TIMESTAMP BY EntryTime  
```  
  
  
