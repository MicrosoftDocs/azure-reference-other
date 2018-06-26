---
title: "orderby clause (Query Syntax in U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "07/01/2018"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
caps.latest.revision: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# orderby clause (Query Syntax in U-SQL)
In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either `ascending` or `descending` order. 

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
 
 
**Basic Syntax**  
```sql
DECLARE @fruits = new SQL.ARRAY<string>{"cherry", "apple", "blueberry"};

DECLARE @sortAscendingQuery =
            from fruit in @fruits
            orderby fruit 
            select fruit;

DECLARE @sortDescendingQuery =
            from w in @fruits
            orderby w descending
            select w; 

// Alternative native method
@result1c = 
        SELECT T.value AS nativeSort              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@fruits) AS T(value)
        ORDER BY T.value FETCH 3 ROWS;


@result1a = 
        SELECT T.value AS sortAscendingQuery              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@sortAscendingQuery) AS T(value);

@result1b = 
        SELECT T.value AS sortDescendingQuery              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@sortDescendingQuery) AS T(value);


OUTPUT @result1a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/orderby/example1a.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result1b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/orderby/example1b.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result1c
TO "/ReferenceGuide/cSharp/LINQ/Keywords/orderby/example1c.txt"
USING Outputters.Tsv(outputHeader: true);
```
 
**Additional Example**  
```sql   
DECLARE @students = new SQL.MAP<string, string>{
                    {"Svetlana", "Omelchenko"},
                    {"Claire", "O'Donnell"},
                    {"Sven", "Mortensen"},
                    {"Cesar", "Garcia"},
                    {"Debra", "Garcia"}
                    };

DECLARE @sortedStudents  =
            from student in @students
            orderby student.Value,  student.Key
            select student;

// Native method
@result2b = 
        SELECT  T.value AS Last,
                T.key AS First              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@students) AS T(key, value)
        ORDER BY T.value, T.key FETCH 5 ROWS ;


@result2a = 
        SELECT  T.value AS Last,
                T.key AS First              
        FROM (VALUES(1)) AS A(x)
        CROSS APPLY EXPLODE (@sortedStudents) AS T(key, value);

OUTPUT @result2a
TO "/ReferenceGuide/cSharp/LINQ/Keywords/orderby/example2a.txt"
USING Outputters.Tsv(outputHeader: true);

OUTPUT @result2b
TO "/ReferenceGuide/cSharp/LINQ/Keywords/orderby/example2b.txt"
USING Outputters.Tsv(outputHeader: true);
```
 
## See Also
* [orderby clause (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/orderby-clause)
* [OrderBy (Method Syntax in U-SQL)](orderby-method-syntax-in-u-sql.md)
* [OUTPUT: Order_By_Opt_Fetch_Clause (U-SQL)](output-statement-u-sql#OBOFC)
* [Enumerable.OrderBy (System.Linq)](https://docs.microsoft.com/dotnet/api/system.linq.enumerable.orderby)
* [ascending (C# Reference)](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/ascending)
* [LINQ Inline Usage in U-SQL](linq-inline-usage-in-u-sql.md)
