---
title: "EXCEPT Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "10/17/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 48626c8d-1c4d-4511-a471-955d99ec71b0
caps.latest.revision: 18
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# EXCEPT Expression (U-SQL)
EXCEPT returns the rows from the left query expression that are not in the right query expression, thus subtracting the right rowset from the left.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Except_Expression :=                                                                                     
    <a href="#qry_exp">Query_Expression</a> 'EXCEPT' [<a href="#SOO">Set_Operator_Option</a>] [<a href="#ByName">By_Name</a>] 
    <a href="#qry_exp">Query_Expression</a>.<br />
<a href="#SOO">Set_Operator_Option</a> :=  
    '<a href="#dist">DISTINCT</a>'  
|   '<a href="#ALL">ALL</a>'.<br />
<a href="#ByName">By_Name</a> :=
    'BY' 'NAME' ['ON' '(' (Identifier_List [',' '*'] | '*') ')'.
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
-   <a name="qry_exp"></a>**`Query_Expression`**   
    Specifies the two input rowsets. The basic rules for combining the result sets of the two query expressions are:  
    -   The number and the order of the columns must be the same in all queries.  
    -   The data types must be compatible and comparable.  
  
    If the number of columns do not match, an error is raised. If the columns are out of order, an error may be raised if the column data types are incompatible. Otherwise an unexpected result may be returned. If the column data types of the two query expressions are incompatible, an error is raised. 
         
    > [!NOTE]
    > The column names do not have to be the same between the two rowsets. The column names of the first rowset is chosen for the result.
  
-   <a name="SOO"></a>**`Set_Operator_Option`**    
    The optional set operator option indicates the handling of duplicate result rows:  
- <a name="dist"></a>**`DISTINCT`**  
Removes duplicate rows from the result (default if the option is left away).
  
- <a name="ALL"></a>**`ALL`**  
Preserves duplicate rows in the result.  
    
    > [!TIP]
    > Unless duplicate elimination is required, specifying `ALL` leads to more efficient execution.
    
- <a name="ByName"></a>**`By_Name`**  
The optional `BY NAME` clause indicates that the exception is matching up values not based on position but by name of the columns. If the `BY NAME` clause is not specified, the matching is done positionally.

  If there is no `ON` clause, the counts of columns on the two sides must be the same and all columns on the left side must have matching columns with the same name on the right side. The schema of the result is the same as the schema of the left argument, i.e., the left argument determines the name and order of the output columns.

  If there is an `ON` clause, it specifies the set of matching columns on both sides. There must be no duplicates in the list or an error is raised. All matching columns must be present in both rowset arguments or an error is raised. Moreover, the specified set of matching columns must be exactly the set of all columns in the two rowsets that have matching names. If there is an extra match that is not listed in the `ON` clause, an error is raised unless a “*” is specified in the list. The two rowsets may have other, non-matching columns, that are ignored by the set operator. The resulting schema is composed only of the matching columns in the order they are present in the left argument.
  
  If the `ON` clause includes the “*” symbol (it may be specified as the last or the only member of the list), then extra name matches beyond those in the `ON` clause are allowed, and the result’s columns include all matching columns in the order they are present in the left argument.  

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the datasets defined below.  Ensure your execution includes the rowset variables.  

#### **Dataset**    
```sql
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
All distinct `id`, `name` values from `@left` that do not exist in `@right`.
```sql
@result =    
    SELECT id, name FROM @left
    EXCEPT DISTINCT    // Using DISTINCT is optional as it is the default value
    SELECT id, name FROM @right;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/EXCEPT/except_distinct_position.txt" 
USING Outputters.Csv();
```

**Return distinct values by name**    
All distinct `id`, `name` values from `@left` that do not exist in `@right`.
```sql
@result = 
    SELECT * FROM @left
    EXCEPT DISTINCT BY NAME ON (*)
    SELECT * FROM @right;  

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/EXCEPT/except_distinct_name.txt" 
USING Outputters.Csv();
```

**Return values with duplicates by position**    
All `id`, `name` values, including duplicates, from `@left` that do not exist in `@right`.
```sql
@result =    
    SELECT id, name FROM @left
    EXCEPT ALL   // ALL preserves duplicates
    SELECT id, name FROM @right;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/EXCEPT/except_all_position.txt" 
USING Outputters.Csv();
```

**Return values with duplicates by name**    
All `id`, `name` values, including duplicates, from `@left` that do not exist in `@right`.
```sql
@result =    
    SELECT * FROM @left
    EXCEPT ALL BY NAME ON (id, *)   
    SELECT * FROM @right;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/EXCEPT/except_all_name.txt" 
USING Outputters.Csv();
```

**EXCEPT with ORDER BY and FETCH**   
The [ORDER BY clause with FETCH](order-by-and-offset-fetch-clause-u-sql.md) allows the selection of a limited number of rows based on the specified order.
```sql
// Data sets
@Product = 
    SELECT * FROM 
        ( VALUES
        (1, "Adjustable Race", "AR-5381", (string)null),
        (2, "Bearing Ball", "BA-8327", (string)null),
        (3, "BB Ball Bearing", "BE-2349", (string)null),
        (4, "Headset Ball Bearings", "BE-2908", (string)null),
        (316, "Blade", "BL-2036", (string)null),
        (317, "LL Crankarm", "CA-5965", "Black"),
        (318, "ML Crankarm", "CA-6738", "Black"),
        (319, "HL Crankarm", "CA-7457", "Black"),
        (320, "Chainring Bolts", "CB-2903", "Silver"),
        (324, "Chain Stays", "CS-2812", (string)null)
        ) AS T(ProductID, Name, ProductNumber, Color);

@WorkOrder = 
    SELECT * FROM 
        ( VALUES
        (88, 3, 4600, new DateTime(2017, 2, 14)),
        (89, 324, 1148, new DateTime(2018, 6, 14)),
        (129, 3, 40, new DateTime(2017, 6, 15)),
        (130, 324, 8, new DateTime(2018, 6, 15)),
        (142, 316, 8, new DateTime(2017, 3, 15)),
        (170, 3, 50, new DateTime(2017, 6, 16)),
        (184, 316, 10, new DateTime(2017, 6, 16)),
        (201, 3, 20, new DateTime(2017, 8, 17)),
        (213, 316, 4, new DateTime(2017, 6, 17)),
        (312, 2, 30, new DateTime(2016, 7, 20))
        ) AS T(WorkOrderID, ProductID, OrderQty, DueDate);


// All products without orders
@result =    
    SELECT ProductID FROM @Product
    EXCEPT ALL 
    SELECT ProductID FROM @WorkOrder;

OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/EXCEPT/Products_wo_Orders.txt" 
USING Outputters.Csv();


// Pull top 5 most recent work orders, thus excluding older orders
@WorkOrder_subset = 
    SELECT * FROM @WorkOrder ORDER BY DueDate DESC FETCH 5 ROWS;

// All products without orders from `@WorkOrder_subset`.
@result =    
    SELECT ProductID FROM @Product 
    EXCEPT ALL
    SELECT ProductID FROM @WorkOrder_subset;
    
// Note that ProductID 2 is now included in the output
OUTPUT @result 
TO "/ReferenceGuide/QSE/Set/EXCEPT/Products_wo_Orders_subset.txt" 
USING Outputters.Csv();
```

### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
* [Set Rowset Expressions (U-SQL)](set-rowset-expressions-u-sql.md)
* [INTERSECT Expression (U-SQL)](intersect-expression-u-sql.md)
* [UNION and OUTER UNION Expression (U-SQL)](union-and-outer-union-expression-u-sql.md) 


