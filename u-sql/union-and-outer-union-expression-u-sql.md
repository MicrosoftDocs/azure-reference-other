---
title: "UNION and OUTER UNION Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-10-17"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9779ed25-b552-444c-9659-8d255222278d
caps.latest.revision: 22
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# UNION and OUTER UNION Expression (U-SQL)
UNION returns all the rows from both the left and right input query expressions.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Union_Expression :=                                                                                      
     <a href="#qry_exp">Query_Expression</a> ['<a href="#outer">OUTER</a>'] 'UNION' [<a href="#SOO">Set_Operator_Option</a>] [<a href="#ByName">By_Name</a>] [<a href="#dj_hnt">Disjoint_Hint</a>]  
     <a href="#qry_exp">Query_Expression</a>.<br />
<a href="#SOO">Set_Operator_Option</a> :=
     '<a href="#dist">DISTINCT</a>'  
|    '<a href="#ALL">ALL</a>'.<br />  
<a href="#ByName">By_Name</a> :=
     'BY' 'NAME' ['ON' '(' (Identifier_List [',' '*'] | '*') ')'.
</pre></td></tr></table>

### Semantics of Syntax Elements  
- <a name="qry_exp"></a>**`Query_Expression`**   
Specifies the two rowsets that are being unioned. The basic rules for combining the result sets of the two query expressions are:  
    -   The number and the order of the columns must be the same in all queries.  
    -   The data types must be compatible and comparable.  
  
  If the number of columns do not match, an error is raised. If the columns are out of order, an error may be raised if the column data types are incompatible. Otherwise an unexpected result may be returned. If the column data types of the two query expressions are incompatible, an error is raised.
         
  > [!NOTE]
  > The column names do not have to be the same between the two rowsets. The column names of the first rowset is chosen for the result.
    
-   <a name="outer"></a>**`OUTER`**     
    `OUTER` requires the `BY NAME` clause and the `ON` list. As opposed to the other set expressions, the output schema of the `OUTER UNION` includes both the matching columns and the non-matching columns from both sides. This creates a situation where each row coming from one of the sides has "missing columns" that are present only on the other side. For such columns, default values are supplied for the "missing cells". The default values are null for nullable types and the .Net default value for the non-nullable types (e.g., 0 for int).

    As opposed to the other set expressions, `OUTER UNION` defaults to the `ALL` set option. The `DISTINCT` option is not supported.
  
-   <a name="SOO"></a>**`Set_Operator_Option`**    
    The optional set operator option indicates the handling of duplicate result rows:  
  
- <a name="dist"></a>**`DISTINCT`**  
Removes duplicate rows from the result (default if the option is left away) .  
  
- <a name="ALL"></a>**`ALL`**  
Preserves duplicate rows in the result.  

  > [!TIP]
  > Unless duplicate elimination is required, specifying `ALL` leads to more efficient execution.

- <a name="ByName"></a>**`By_Name`**  
`BY NAME` is required when used with `OUTER`.  The clause indicates that the union is matching up values not based on position but by name of the columns. If the `BY NAME` clause is not specified, the matching is done positionally.

  If there is no `ON` clause, the counts of columns on the two sides must be the same and all columns on the left side must have matching columns with the same name on the right side. The schema of the result is the same as the schema of the left argument, i.e., the left argument determines the name and order of the output columns.

  If there is an `ON` clause, it specifies the set of matching columns on both sides. There must be no duplicates in the list or an error is raised. All matching columns must be present in both rowset arguments or an error is raised. Moreover, the specified set of matching columns must be exactly the set of all columns in the two rowsets that have matching names. If there is an extra match that is not listed in the `ON` clause, an error is raised unless a “*” is specified in the list. The two rowsets may have other, non-matching columns, that are ignored by the set operator. The resulting schema is composed only of the matching columns in the order they are present in the left argument.
  
  If the `ON` clause includes the “*” symbol (it may be specified as the last or the only member of the list), then extra name matches beyond those in the `ON` clause are allowed, and the result’s columns include all matching columns in the order they are present in the left argument.
  
- <a name="dj_hnt"></a>**`Disjoint_Hint`**    
  Provides the hint that any tuple of the list of specified columns appear in at most one of the input rowsets.  
  
  <table><th>Syntax</th><tr><td><pre>
  Disjoint_Hint :=                                                                                    
       'WITH' 'DISJOINT' '(' Identifier_List ')'.
  </pre></td></tr></table>
      
    This optimization hint allows that any later [GROUP BY](group-by-and-having-clauses-u-sql.md) clause on those columns can be pushed through the `UNION ALL` expression to the rowset expressions.  
  
    For example, rows containing the same values in the market column only appear in one of the input rowsets. E.g., only one of the rowsets contain the “en-us” values. If the disjoint hint WITH DISJOINT (market) has been specified, then a later [GROUP BY](group-by-and-having-clauses-u-sql.md) market is pushed into the rowset expressions, thus improving the query performance.  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the datasets defined below.  Ensure your execution includes the rowset variables.  

**Dataset**    
```
@left = 
    SELECT * FROM 
        ( VALUES
        (1,	"Smith", 20),
        (1,	"Smith", 20),
        (1,	"Smith", 20),
        (2,	"Brown", 30),
        (3,	"Case", 40),
        (4, (string)null, 45),
        (5, (string)null, 50)
        ) AS T(id, name, age);

@right = 
    SELECT * FROM 
        ( VALUES
        (1, 20000,	"Smith"),
        (1, 20000,	"Smith"),
        (2, 30000,	"Brown"),
        (2, 30000,	"Brown"),
        (4, 50000,	"Dey"),
        (4, 50000,	"Dey"),
        (5, 60000, (string)null)
        ) AS T(id, salary, name);
```

**Return distinct values by position**   
All distinct `id`, `name` values from `@left` and `@right`.
```
@result =    
    SELECT id, name FROM @left
    UNION DISTINCT      // Using DISTINCT is optional as it is the default value
    SELECT id, name FROM @right;  

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/UNION/union_distinct_position.txt" 
USING Outputters.Csv();
```

**Return distinct values by name**    
All distinct `id`, `name` values from `@left` and `@right`.
```
@result = 
    SELECT * FROM @left
    UNION DISTINCT BY NAME ON (*)
    SELECT * FROM @right;  

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/UNION/union_distinct_name.txt" 
USING Outputters.Csv();
```

**Return values with duplicates by position**     
All `id`, `name` values, including duplicates, from `@left` and `@right`.
```
@result =    
    SELECT id, name FROM @left
    UNION ALL   // ALL preserves duplicates
    SELECT id, name FROM @right;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/UNION/union_all_position.txt" 
USING Outputters.Csv();
```

**Return values with duplicates by name**     
All `id`, `name` values, including duplicates, from `@left` and `@right`.
```
@result =    
    SELECT * FROM @left
    UNION ALL BY NAME ON (id, *)   
    SELECT * FROM @right;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/UNION/union_all_name.txt" 
USING Outputters.Csv();
```

**Return all records with OUTER UNION**   
Returns matching columns and non-matching columns from both `@left` and `@right`.
```
@result =    
    SELECT * FROM @left
    OUTER UNION ALL BY NAME ON (id, name)   // DISTINCT is not supported
    SELECT * FROM @right;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/UNION/outer_union_all_name.txt" 
USING Outputters.Csv(outputHeader: true);

// same as above
@result =    
    SELECT id, name, age FROM @left
    OUTER UNION BY NAME ON (*) 
    SELECT id, name, salary FROM @right;

OUTPUT @result 
TO "/Output/ReferenceGuide/Operators/Set/outer_union_all_name2.txt" 
USING Outputters.Csv(outputHeader: true);
```

**UNION with ORDER BY and FETCH**   
The [ORDER BY clause with FETCH](order-by-and-offset-fetch-clause-u-sql.md) allows the selection of a limited number of rows based on the specified order.
```
// Data sets
@JuneSales = 
    SELECT * FROM 
        ( VALUES
        (43707, new DateTime(2011, 6, 2), 27616, 3953.99f),
        (43708, new DateTime(2011, 6, 2), 20042, 772.50f),
        (43713, new DateTime(2011, 6, 4), 27601, 3953.99f),
        (43729, new DateTime(2011, 6, 8), 11238, 3756.99f),
        (43732, new DateTime(2011, 6, 8), 11025, 3729.36f),
        (43843, new DateTime(2011, 6, 9), 29955, 37106.29f),
        (43844, new DateTime(2011, 6, 11), 29620, 22801.43f),
        (43845, new DateTime(2011, 6, 13), 29888, 9661.14f),
        (43846, new DateTime(2011, 6, 19), 29548, 1038.52f),
        (43847, new DateTime(2011, 6, 21), 29539, 1022.92f)
        ) AS T(SalesOrderID, OrderDate, CustomerID, TotalDue);

@JulySales = 
    SELECT * FROM 
        ( VALUES
        (43848, new DateTime(2011, 7, 1), 29717, 20571.96f),
        (43849, new DateTime(2011, 7, 1), 29818, 23130.30f),
        (43850, new DateTime(2011, 7, 1), 29892, 11473.90f),
        (43851, new DateTime(2011, 7, 1), 29509, 7638.86f),
        (43852, new DateTime(2011, 7, 1), 29855, 2280.14f),
        (43853, new DateTime(2011, 7, 1), 29813, 29675.64f),
        (43854, new DateTime(2011, 7, 1), 29988, 1970.04f),
        (43855, new DateTime(2011, 7, 1), 29946, 12382.92f),
        (43923, new DateTime(2011, 7, 2), 28018, 3953.99f),
        (43926, new DateTime(2011, 7, 3), 11055, 3729.36f)
        ) AS T(SalesOrderID, OrderDate, CustomerID, TotalDue);

// June & July sales
@result =    
    SELECT * FROM @JuneSales
    UNION ALL 
    SELECT * FROM @JulySales;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/UNION/allSales.txt" 
ORDER BY OrderDate ASC
USING Outputters.Tsv();


// Top 5 June sales by TotalDue
@topJuneSales = 
    SELECT * FROM @JuneSales ORDER BY TotalDue DESC FETCH 5 ROWS;

// Then combined with all of July sales
@result =    
    SELECT * FROM @topJuneSales
    UNION ALL 
    SELECT * FROM @JulySales;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/UNION/TopJuneAllJuly.txt" 
ORDER BY OrderDate ASC
USING Outputters.Tsv();
```

**Additional examples using OUTER UNION**   
See the examples under [SQL.MAP](complex-built-in-u-sql-types.md#sqlMAP) which make use of `OUTER UNION`.

### See Also
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md)
* [Set Rowset Expressions (U-SQL)](set-rowset-expressions-u-sql.md)
* [EXCEPT Expression (U-SQL)](except-expression-u-sql.md)
* [INTERSECT Expression (U-SQL)](intersect-expression-u-sql.md)
* [Output Statement (U-SQL)](output-statement-u-sql.md)  
