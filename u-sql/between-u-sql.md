---
title: "BETWEEN (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bda15970-9efb-4f2e-a6a1-4d0c423dc65c
caps.latest.revision: 5
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# BETWEEN (U-SQL)
The `BETWEEN` operator allows to compare a value against a data type specific range and returns true if the value is within the range given by the lower and upper bounds inclusive both boundaries, false otherwise. The types of the expressions have to be compatible or an error is raised.  

```sql  
a BETWEEN b AND c is equivalent to b <= a AND a <= c. 
Since the rewrite of BETWEEN will execute the expression a twice, it should be a deterministic expression.  
```
Note that the comparison is using C# comparison semantics, especially regarding `null` values.  
  
<table><th align="left">Syntax</th><tr><td><pre>
BETWEEN_Expression :=                                                                                    
     <a href="#exp">expression</a> 'BETWEEN' <a href="#LB">Lowerbound</a> 'AND' <a href="#UB">Upperbound</a>.<br />

<a href="#LB">Lowerbound</a> :=
<a href="#exp">     expression</a>.<br />
<a href="#UB">Upperbound</a> :=
<a href="#exp">     expression</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="exp"></a>**`expression`**  
    is the expression that returns the value that gets compared against the range. The type of the expression has to be a comparable type, otherwise an error is raised. The expression should be deterministic because it will be executed twice in the rewrite..  
  
-   <a name="LB"></a>**`Lowerbound`**   
    is the expression that returns the value of the lower bound. The type of the expression has to be compatible with the expression type, otherwise an error is raised.   
  
-   <a name="UB"></a>**`Upperbound`**    
    is the expression that returns the value of the upper bound. The type of the expression has to be compatible with the expression type, otherwise an error is raised.   
  
### Return Type    
[bool](other-simple-built-in-types-and-literals.md)  
  
### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

```sql
@data  = 
    SELECT * FROM 
        (VALUES  
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14)),
        (11, "Ethan", 400, (int?)null,  new DateTime(2015,08,22))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);

@result =
    SELECT * FROM @data
    WHERE EmpID BETWEEN 3 AND 10;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Between1.txt" USING Outputters.Csv();


// alternative
@result =
    SELECT * FROM @data
    WHERE EmpID >= 3 AND EmpID <= 10;

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Between2.txt" USING Outputters.Csv();


@result =
    SELECT * FROM @data
    WHERE StartDate BETWEEN DateTime.Parse("2012/03/15") AND DateTime.Parse("2012/05/31");

OUTPUT @result TO "/ReferenceGuide/Operators/Logical/Between3.txt" USING Outputters.Csv();
```
  
### See Also 
* [Comparison Operators (U-SQL)](comparison-operators-u-sql.md)  
* [IN, NOT IN (U-SQL)](in-not-in-u-sql.md)  
* [LIKE, NOT LIKE (U-SQL)](like-not-like-u-sql.md)  
* [C# Operators](https://msdn.microsoft.com/library/6a71f45d.aspx) 
