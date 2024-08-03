---
title: "SELECT (Azure Stream Analytics)"
description: "Retrieves rows from input streams and enables the selection of one or many columns from one or many input streams in Azure Stream Analytics."
applies_to: 
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# SELECT (Azure Stream Analytics)
  Retrieves rows from input streams and enables the selection of one or many columns from one or many input streams in Azure Stream Analytics. The main clauses used with a SELECT expression can be summarized as:  
  
```SQL   
[ WITH <Result_Set_name>]   
SELECT select_list   
FROM input_source [TIMESTAMP BY column_name ] [PARTITION BY column_name ]   
[ WHERE search_condition ]   
[ GROUP BY group_by_expression ]   
[ HAVING search_condition ]  
  
```  
  
 ## Syntax  
  
```SQL   
SELECT <select_list>   
<select_list> ::=   
    {   
      *   
      | { input_name |  input_alias }.*   
      | {  
          [ { input_name | input_alias }. ]  
               { column_name }  
     | expression [ [ AS ] column_alias ]  
         }  
      | column_alias = expression   
    } [ ,...n ]  
  
```  
  
## Arguments  
 **\***  
  
 Specifies that all columns from all input streams in the FROM clause should be returned. The columns are returned by input source, as specified in the FROM clause, and in the order in which they exist in the incoming stream.  
  
 **input_name | input_alias.\***  
  
 Limits the scope of the * to the specified input name.

**column_name.\***

For columns of type Record (complex object) return all nested fields as individual columns.

Columns from * expression with names conflicting with previously projected columns in the same SELECT statement are ignored. Columns on the left side of the SELECT statement take precedence over columns on the right.

  
 **column_name**  
  
 Is the name of a column to return. Qualify column_name to prevent an ambiguous reference, such as occurs when two input source in the FROM clause have columns with duplicate names.  
  
 **expression**  
  
 Is a constant, function, any combination of column names, constants, and functions connected by an operator or operators, or a subquery.  
  
 **column_alias**  
  
 Is an alternative name to replace the column name in the query result set. For example, an alias such as Quantity, or [Quantity to Date], or Qty can be specified for a column named quantity. Aliases are used also to specify names for the results of expressions. column_alias cannot be used in a WHERE, GROUP BY, or HAVING clause.  

## Remark

To access a field or property that uses characters that need to be escaped, double quotes can be used: `SELECT "[my][Field]" AS myField ...`.

## Example  
  
```SQL  
SELECT TollId, EntryTime AS VehicleEntryTime, LicensePlate, State, Make, Model, VehicleType, VehicleWeight, Toll, Tag   
FROM TollTagEntry TIMESTAMP BY EntryTime  
  
```  
  
  
