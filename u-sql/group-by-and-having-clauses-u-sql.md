---
title: "GROUP BY and HAVING Clauses (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 293710a5-937d-469f-beb4-c3531c799da0
caps.latest.revision: 12
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# GROUP BY and HAVING Clauses (U-SQL)
The optional GROUP BY clause groups the rows based on the provided expression list into groups that then can be aggregated over with the built-in and [user-defined aggregators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg). It offers an optional filter clause with HAVING that will filter the rowset at the group level. In other words, the predicate in the HAVING clause will be applied to the group and will only include the groups for which it evaluates to true.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Group_By_Clause :=                                                                                       
    'GROUP' 'BY' <a href="#exp_lst">Expression_List</a> [<a href="#hav_cla">Having_Clause</a>]<br />
<a href="#hav_cla">Having_Clause</a> :=  
    'HAVING' Boolean_Expression
</pre></td></tr></table>
  
### Semantics of Syntax Elements  
-   <a name="exp_lst"></a>**`Expression_List`**   
    Provides the list of expressions and column references that define the hierarchical grouping. The groups are built from left to right: the left most expression defines the outer group, every subsequent expression defines a group inside the previous group. In the end all groups are flattened into a set of groups on which the aggregations will occur.  
  
    Note that the [SELECT clause](select-clause-u-sql.md) in a [SELECT expression](select-expression-u-sql.md) with a GROUP BY has to contain only the columns or expressions that appear in the `GROUP BY`’s expression list and the aggregation expressions. Otherwise an error is raised.  Expressions or column references in the GROUP BY do not have to be in the [SELECT clause](select-clause-u-sql.md), even though they are being used to define the groups.  
  
-   <a name="hav_cla"></a>**`Having_Clause`**   
    The `HAVING` clause offers an optional filter clause that will filter the rowset at the group level.  In other words, the predicate in the `HAVING` clause will be applied to the group and will only include the groups for which it evaluates to true.  
  
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following query uses the GROUP BY clause to provide us with the total number of employees in each department.  
```
@employees = SELECT *
               FROM (VALUES   
                      ("Rafferty", (int?) 31)  
                    , ("Jones", (int?) 33)  
                    , ("Heisenberg", (int?) 33)  
                    , ("Robinson", (int?) 34)  
                    , ("Smith", (int?) 34)  
                    , ("Williams", (int?) null)) AS E(EmpName, DepID);  
                      
@departments = SELECT *  
                FROM (VALUES  
                       ((int) 31, "Sales")  
                     , ((int) 33, "Engineering")  
                     , ((int) 34, "Clerical")  
                     , ((int) 35, "Marketing")) AS D(DepID, DepName);  
  
@rs_group_by =   
    SELECT d.DepName, COUNT(EmpName) AS TotalEmployees  
    FROM (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d   
          LEFT OUTER JOIN @employees AS e  
         ON d.DepID == e.DepID  
    GROUP BY d.DepName;  
  
OUTPUT @rs_group_by   
TO "/output/rsGroupBy.csv"  
USING Outputters.Csv();
```
The following query uses the GROUP BY and HAVING clauses to provide us with the number of employees in each department that has at least one employee.  
  
```
@employees = SELECT *  
               FROM (VALUES   
                      ("Rafferty", (int?) 31)  
                    , ("Jones", (int?) 33)  
                    , ("Heisenberg", (int?) 33)  
                    , ("Robinson", (int?) 34)  
                    , ("Smith", (int?) 34)  
                    , ("Williams", (int?) null)) AS E(EmpName, DepID);  
                      
@departments = SELECT *  
                FROM (VALUES  
                       ((int) 31, "Sales")  
                     , ((int) 33, "Engineering")  
                     , ((int) 34, "Clerical")  
                     , ((int) 35, "Marketing")) AS D(DepID, DepName);  
  
@rs_having =   
    SELECT d.DepName, COUNT(EmpName) AS TotalEmployees  
    FROM (SELECT (int?) DepID AS DepID, DepName FROM @departments) AS d   
          LEFT OUTER JOIN @employees AS e  
         ON d.DepID == e.DepID  
    GROUP BY d.DepName  
    HAVING COUNT(EmpName) > 0;  
  
OUTPUT @rs_having   
TO "/output/rsHaving.csv"  
USING Outputters.Csv();
```
   
### See Also 
* [Query Statements and Expressions (U-SQL)](query-statements-and-expressions-u-sql.md) 
* [SELECT Expression (U-SQL)](select-expression-u-sql.md) 
* [Output Statement (U-SQL)](output-statement-u-sql.md)  

