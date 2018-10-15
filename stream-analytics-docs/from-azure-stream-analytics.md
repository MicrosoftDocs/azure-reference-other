---
title: "FROM (Azure Stream Analytics) | Microsoft Docs"
description: "Specifies the input stream or a step name associated in a WITH clause. The FROM clause is always required for any SELECT statement."
applies_to: 
  - "Azure"
services: stream-analytics
author: mamccrea
manager: kfile

ms.service: stream-analytics
ms.topic: reference
ms.assetid: 4b6f2a98-fceb-4066-ba43-1957a47f1859
caps.latest.revision: 6
ms.workload: data-services
ms.date: 04/22/2016
ms.author: mamccrea
---
# FROM (Azure Stream Analytics)
  Specifies the input stream or a step name associated in a WITH clause. The FROM clause is always required for any SELECT statement.  
  
 ## Syntax  
  
```  
[ FROM { <input_source> } [ ,...n ] ]  
  
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
    } [ ,...n ]  
  
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
  
## Example  
  
```SQL  
SELECT TollId, EntryTime AS VehicleEntryTime, LicensePlate, State, Make, Model, VehicleType, VehicleWeight, Toll, Tag   
FROM TollTagEntry TIMESTAMP BY EntryTime  
  
```  
  
  
