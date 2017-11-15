---
title: "MAP_AGG (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-14"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: edb9ee42-42cc-4b53-bac2-8f6467f03861
caps.latest.revision: 12
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# MAP_AGG (U-SQL)
The MAP_AGG aggregator takes a key, value pair and creates a [SQL.MAP](../u-sql/complex-built-in-u-sql-types.md) for all the key/value pairs in the group. 

MAP_AGG and [EXPLODE](../u-sql/explode-u-sql.md) are conceptually inverse operations. 

The identity value is null. 

<table><th align="left">Syntax</th><tr><td><pre>
MAP_AGG_Expression :=                                                                                    
     'MAP_AGG' '(' ['<a href="#dist">DISTINCT</a>'] <a href="#k_exp">Key_Expression</a>, <a href="#v_exp">Value_Expression</a> ')'.<br /> 
<a href="#k_exp">Key_Expression</a> := 
     expression.<br />
<a href="#v_exp">Value_Expression</a> := 
     expression.
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**    
Optionally allows to de-duplicate the values returned by the expression inside the group before aggregation.  

* <a name="k_exp"></a>**`Key_Expression`**     
The C# expression (including column references) that will define the keys. Its type has to be a type that is acceptable as a [SQL.MAP](../u-sql/complex-built-in-u-sql-types.md) key or an error is raised.  

* <a name="v_exp"></a>**`Value_Expression`**     
The C# expression (including column references) that will define the values. Its type has to be a type that is acceptable as a [SQL.MAP](../u-sql/complex-built-in-u-sql-types.md) value or an error is raised. 

### Return Type 
[SQL.MAP](../u-sql/complex-built-in-u-sql-types.md)\<K,V\> where K is the type of the key expression and V is the type of the value expression. 

### Usage in Windowing Expression 
This aggregator cannot be used in a [windowing expression](../u-sql/over-expression-u-sql.md). 

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

**MAP_AGG**   
This example takes a key, value pair (`PhoneType` and `PhoneNumber`) and creates a [SQL.MAP](../u-sql/complex-built-in-u-sql-types.md) for all the key/value pairs in the group, `EmpName`.   
This example provides an alternative solution to [Using User Defined Aggregator - genericAggregator A](../u-sql/extending-u-sql-expressions-with-user-code.md#genericAggA).
```
@employees = 
    SELECT * FROM 
        ( VALUES
        ("Noah",   "cell",   "030-0074321"),
        ("Noah",   "office", "030-0076545"),
        ("Sophia", "cell",   "(5) 555-4729"),
        ("Sophia", "office", "(5) 555-3745"),
        ("Liam",   "cell",   "(5) 555-3932"),
        ("Amy",    "cell",   "(171) 555-7788"),
        ("Amy",    "office", "(171) 555-6750"), 
        ("Amy",    "home",   "(425) 555-6238"),
        ("Justin", "cell",   "0921-12 34 65"),
        ("Justin", "office", "0921-12 34 67"),
        ("Emma",   (string)null, (string)null),
        ("Jacob",  "", ""),
        ("Olivia", "cell",   "88.60.15.31"),
        ("Olivia", "office", "88.60.15.32"),
        ("Mason",  "cell",   "(91) 555 22 82"),
        ("Mason",  "office", "(91) 555 91 99"), 
        ("Mason",  "home",   "(425) 555-2819"),
        ("Ava",    "cell",   "91.24.45.40"),
        ("Ava",    "office", "91.24.45.41"),
        ("Ethan",  "cell",   "(604) 555-4729"),
        ("Ethan",  "office", "(604) 555-3745"),
        ("David",  "cell",   "(171) 555-1212"),
        ("Andrew", "cell",   "(1) 135-5555"),
        ("Andrew", "office", "(1) 135-4892"),
        ("Jennie", "cell",   "(5) 555-3392"),
        ("Jennie", "office", "(5) 555-7293")
        ) AS T(EmpName, PhoneType, PhoneNumber);
        
@result =
    SELECT EmpName,
           String.Join(",", MAP_AGG(PhoneType, PhoneNumber).Select(p => String.Format("{0}:{1}", p.Key, p.Value))).Trim() AS PhoneNumbers
    FROM @employees
    WHERE !string.IsNullOrWhiteSpace(PhoneType)
    GROUP BY EmpName;

OUTPUT @result
TO "/Output/ReferenceGuide/Aggregate/map_agg/exampleA.csv"
USING Outputters.Csv();      
```

**EXPLODE - Bonus Example**   
This example does not use `MAP_AGG`; however, it illustrates how to reverse the outcome from the above example using [EXPLODE](../u-sql/explode-u-sql.md).
```
@map =
    SELECT EmpName,
           PhoneNumbers == ""? null : new SQL.MAP<string, string>(from p in PhoneNumbers.Split(',') select new KeyValuePair<string, string>(p.Split(':') [0], p.Split(':') [1])) AS PhoneNumberMap
    FROM @result
    WHERE PhoneNumbers != null;

@exploded =
    SELECT EmpName,
           r.key.Trim() AS PhoneType,
           r.value AS PhoneNumber
    FROM @map
    CROSS APPLY
    EXPLODE(PhoneNumberMap) AS r(key, value);

OUTPUT @exploded
TO "/Output/ReferenceGuide/Aggregate/map_agg/exampleB.csv"
USING Outputters.Csv();
```

**MAP_AGG - Additional Example**  
The query uses `MAP_AGG` to pivot the sales figures from the `@storeSales` rowset variable.
```
@storeSales =
    SELECT * FROM 
        ( VALUES
        (1, "2013", 100),
        (1, "2014", 150),
        (1, "2015", 300),
        (1, "2016", 400),
        (2, "2013", 200),
        (2, "2014", 350),
        (2, "2015", 500),
        (2, "2016", 650),
        (3, "2014", 75),
        (3, "2015", 100),
        (3, "2016", 80)
        ) AS T(StoreID, Year, Sales);

@salesPrePivot =
    SELECT StoreID,
           MAP_AGG(Year, (int?) Sales) AS Data
    FROM @storeSales
    GROUP BY StoreID;

@results =
    SELECT StoreID,
           Data["2013"] AS [2013],
           Data["2014"] AS [2014],
           Data["2015"] AS [2015],
           Data["2016"] AS [2016]
    FROM @salesPrePivot;

OUTPUT @results
TO "/Output/ReferenceGuide/Aggregate/map_agg/exampleC.csv"
USING Outputters.Csv();
```

**PIVOT and MAP_AGG**<a name="pivot_basic"></a>     
The examples below repro the first two examples from [Using PIVOT and UNPIVOT](https://msdn.microsoft.com/library/ms177410.aspx) in SQL Server.  To execute the example with the same data set, simply bcp or copy and paste `DaysToManufacture` and `StandardCost` from AdventureWorks2014.Production.Product to a local text file.  The same data set appears in at least [AdventureWorks2016](https://www.microsoft.com/download/details.aspx?id=49502).  An alternative solution using PIVOT can be viewed at [Basic PIVOT Example](../u-sql/pivot-and-unpivot-u-sql.md#pivot_basic).
```
@products =
     EXTRACT DaysToManufacture  int,
             StandardCost       double
     FROM "/Samples/Data/Product.txt"
     USING Extractors.Tsv();

// standard non-pivoted aggregate result
@results = 
    SELECT DaysToManufacture, AVG(StandardCost) AS AverageCost
    FROM   @products
    GROUP BY DaysToManufacture;

OUTPUT @results
TO "/Output/ReferenceGuide/Aggregate/map_agg/pivot/exampleA1.csv"
USING Outputters.Csv();


// create key, value pair
@prePivot =
    SELECT "AverageCost" AS Cost_Sorted_By_Production_Days,
           MAP_AGG(DaysToManufacture, (double?)AverageCost) AS Data
    FROM @results;

// pivot SQL.MAP results
@resultsPivot =
    SELECT Cost_Sorted_By_Production_Days,
           Data[0] AS [0],
           Data[1] AS [1],
           Data[2] AS [2],
           Data[3] AS [3],
           Data[4] AS [4]
    FROM @prePivot;

OUTPUT @resultsPivot
TO "/Output/ReferenceGuide/Aggregate/map_agg/pivot/exampleA2.csv"
USING Outputters.Csv(outputHeader: true);
```

**PIVOT and MAP_AGG - Additional Example**<a name="pivot_complex"></a>    
The example below repros the third example, "Complex PIVOT Example", from [Using PIVOT and UNPIVOT](https://msdn.microsoft.com/library/ms177410.aspx).  To execute the example with the same data set, simply bcp or copy and paste `PurchaseOrderID`, `EmployeeID`, and `VendorID` from AdventureWorks2014.Purchasing.PurchaseOrderHeader to a local text file.  The same data set appears in at least [AdventureWorks2016](https://www.microsoft.com/download/details.aspx?id=49502).  An alternative solution using PIVOT can be viewed at [Complex PIVOT Example](../u-sql/pivot-and-unpivot-u-sql.md#pivot_complex).
```
@purchaseOrder =
     EXTRACT PurchaseOrderID int, 
                EmployeeID int, 
                VendorID   int
     FROM "/Samples/Data/PurchaseOrderHeader.txt"
     USING Extractors.Tsv();

// aggregate data
@results = 
    SELECT EmployeeID, VendorID, COUNT(PurchaseOrderID) AS PurchaseOrderID
    FROM @purchaseOrder
    WHERE EmployeeID IN (250, 251, 256, 257, 260)
    GROUP BY EmployeeID, VendorID;

// create key, value pair
@prePivot =
    SELECT VendorID,
           MAP_AGG(EmployeeID, (int?)PurchaseOrderID) AS Data
    FROM @results
    GROUP BY VendorID;

// pivot SQL.MAP results
@resultsPivot =
    SELECT VendorID,
           Data[250] AS Emp1,
           Data[251] AS Emp2,
           Data[256] AS Emp3,
           Data[257] AS Emp4,
           Data[260] AS Emp5
    FROM @prePivot;

OUTPUT @resultsPivot
TO "/Output/ReferenceGuide/Aggregate/map_agg/pivot/exampleB1.csv"
USING Outputters.Csv(outputHeader: true);
```

### See Also 
* [Aggregate Functions (U-SQL)](../u-sql/aggregate-functions-u-sql.md)  
* [GROUP BY and HAVING Clauses (U-SQL)](../u-sql/group-by-and-having-clauses-u-sql.md) 
* [EXPLODE (U-SQL)](../u-sql/explode-u-sql.md)
* [OVER Expression (U-SQL)](../u-sql/over-expression-u-sql.md) 
* [PIVOT and UNPIVOT (U-SQL)](../u-sql/pivot-and-unpivot-u-sql.md) 
