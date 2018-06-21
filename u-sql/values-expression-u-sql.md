---
title: "VALUES Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f4a11b31-0aa3-4d9a-b3f2-942f31a0b4d8
caps.latest.revision: 17
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# VALUES Expression (U-SQL)
U-SQL offers the ability to create a table using constant values using the Table Value Constructor `VALUES` expression that can be used by a [SELECT](select-expression-u-sql.md) expression’s [FROM](from-clause-u-sql.md) clause or by [INSERT](insert-u-sql.md) statement as an input rowset. The names for the columns are provided by the SELECT’s mandatory derived table alias or the target table’s columns in the [INSERT](insert-u-sql.md) case.   
  
## Syntax
<pre>
Table_Value_Constructor_Expression := 
    'VALUES' <a href="#RCL">Row_Constructor_List</a>.
</pre>
  
## Semantics of Syntax Elements  
* <a name="RCL"></a>**`Row_Constructor_List`**   
The `VALUES` constructor takes a list of row constructors that create a value for the column at the given position. Note that each row constructor needs to have the same number of values or an error is raised.  The constructor supports up to 1 million constant values. The limit is based on the total count based on the `number of rows * number of columns`.

  ### Syntax
  <pre>
  Row_Constructor_List := 
      Row_Constructor { ',' Row_Constructor }.<br />
  Row_Constructor := 
      '(' Expression_List ')'.<br />
  Expression_List := 
      expression {',' expression}.
  </pre>
  
  The types for the columns are inferred from the type of the expression in the first row constructor and has to be one of the U-SQL [built-in types](built-in-u-sql-types.md). All subsequent row constructors then have to produce the same types for the same columns and if now, they have to be cast or an error is raised. If any of the column values is null, then the type of all expressions for that column in all row constructor has to be nullable.   
 
## Examples 
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script(s) can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
**Basic Syntax**  
```sql
@data =  
    SELECT * FROM 
        ( VALUES
        (1L, "val1", new DateTime(2000,1,1)),
        (2L, "val2", new DateTime(2000,1,2)),
        (3L, "val3", new DateTime(2000,1,3))
        ) AS table(a, b, c);  
            
OUTPUT @data   
TO "/ReferenceGuide/QSE/Values/example1.txt" 
USING Outputters.Tsv();
```

**Additional Example**   
Similiar to example, above, except this is one record with three columns
```sql
@data = 
    SELECT 
       1L AS a,
       "val1" AS b,
       new DateTime(2000,1,1) AS c
    FROM 
        (VALUES 
        (1)
        ) AS T(a);

OUTPUT @data
TO "/ReferenceGuide/QSE/Values/example2.txt"
USING Outputters.Tsv();
```
   
See additional examples:
* [U-SQL SELECT Selecting from the VALUES Table Value Constructor](u-sql-select-selecting-from-the-values-table-value-constructor.md), and 
* [INSERT (U-SQL)](insert-u-sql.md).  

## See Also 
* [U-SQL SELECT Selecting from the VALUES Table Value Constructor](u-sql-select-selecting-from-the-values-table-value-constructor.md)  
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)  
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
* [INSERT (U-SQL)](insert-u-sql.md)

