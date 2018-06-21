---
title: "ANY_VALUE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 69303dc9-1581-438f-8b74-8171e6340700
caps.latest.revision: 10
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# ANY_VALUE (U-SQL)
The `ANY_VALUE` aggregator arbitrarily picks one value from the group including potentially a null value. While the operation picks an arbitrary value, it does so based on the efficiency of execution and not based on some random sampling. 

The identity value is null. 

## Syntax  
<pre>
ANY_VALUE_Expression :=
    'ANY_VALUE' '(' <a href="#exp">expression</a> ')'.
</pre>

## Semantics of Syntax Elements 

* <a name="exp"></a>**`expression`**  
The C# expression (including column references) that gets aggregated. 

## Return Type 
The type of the input. 

## Usage in Windowing Expression 
This aggregator cannot be used in a [windowing expression](over-expression-u-sql.md). 

## Examples
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).
- The script(s) can be executed [locally]s(https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-local-run).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

**Dataset**  
```sql
@sales = 
    SELECT * FROM 
        ( VALUES
        (1, "A", "Noah",    100, "FA1", new DateTime(2017,01,01)),
        (1, "A", "Noah",    200, "FA1", new DateTime(2017,02,01)),
        (1, "A", "Noah",    300, "FA2", new DateTime(2017,03,01)),
        (1, "A", "Noah",    400, "GA1", new DateTime(2017,04,01)),
        (2, "B", "Sophia",  400, "FA1", new DateTime(2017,01,01)),
        (2, "B", "Sophia",  300, "FA2", new DateTime(2017,02,01)),
        (2, "B", "Sophia",  200, "FA2", new DateTime(2017,03,01)),
        (2, "B", "Sophia",  100, "FA3", new DateTime(2017,04,01)),
        (3, "B", "Liam",    75,  "FA3", new DateTime(2017,04,01))
        ) AS T(EmpID, DeptID, EmpName, Sales, ProductID, SaleDate);
```

**Using ANY_VALUE to optimize query**  
Using `ANY_VALUE` for `EmpName` in this query avoids the need to add `EmpName` to the `GROUP BY` statement and thus one less operation.
```sql
@result =
    SELECT EmpID, ANY_VALUE(EmpName) AS EmpName, SUM(Sales) AS totalSales
    FROM @sales
    GROUP BY EmpID;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/any_value/example1.txt"
USING Outputters.Tsv(outputHeader: true);

/*     
This query would fail with the following error messages:
Every element in a select item must match an expression in GROUP BY exactly unless it is a constant or aggregate function.
Either remove the colum from the select list or add it to the GROUP BY clause.
@result =
    SELECT EmpID, Name, SUM(Sales) AS totalSales
    FROM @sales
    GROUP BY EmpID;
*/
```

**Using ANY_VALUE to select a single arbitrary value**    
The following query selects a single arbitrary `EmpName`. 
```sql
@result =
    SELECT ANY_VALUE(EmpName) AS ArbitraryEmployee
    FROM @sales;

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/any_value/example2.txt"
USING Outputters.Tsv();
```

**Using ANY_VALUE to select a single arbitrary value per group**    
The following query selects an arbitrary `EmpName` for each `DeptName`.
```sql
@result =
    SELECT EmpID,
           ANY_VALUE(EmpName) AS ArbitraryEmployee
    FROM @sales
    GROUP BY EmpID;    

OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/AggFunctions/any_value/example3.txt"
USING Outputters.Tsv();
```

## See Also 
* [Aggregate Functions (U-SQL)](aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [OVER Expression (U-SQL)](over-expression-u-sql.md)
