---
title: "U-SQL SELECT Selecting from Joins | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a3eec714-314c-43f6-9e11-1bf5586eabd5
caps.latest.revision: 21
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# U-SQL SELECT Selecting from Joins
U-SQL provides the following ways of joining two rowsets:  
* [Cross join](cross-join-u-sql.md)
* [full, left, or right outer join](outer-join-u-sql.md)
* [inner join](inner-join-u-sql.md)
* [left or right semijoin](semijoin-u-sql.md)
* [left or right antisemijoin](antisemijoin-u-sql.md)

The syntax follows the ANSI SQL join syntax. The comma separated implicit cross join syntax with a join predicate in a [WHERE (U-SQL)](where-clause-u-sql.md) clause is not supported in U-SQL. Either use an explicit [CROSS JOIN](cross-join-u-sql.md) or preferably use an [INNER](inner-join-u-sql.md) or [OUTER JOIN](outer-join-u-sql.md) instead.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Join_Expression :=                                                                                       
     <a href="#row_src">Rowset_Source</a> <a href="#row_src">Cross_Join_Operator</a> <a href="#row_src">Rowset_Source</a>  
|    <a href="#row_src">Rowset_Source</a> <a href="#join_op">Join_Operator</a> <a href="#row_src">Rowset_Source</a> <a href="#join_on_cl">Join_On_Clause</a>.
</pre></td></tr></table>
  
### Semantics of Syntax Elements
- <a name="row_src"></a>**`Rowset_Source`**   
  Specifies the rowsets that are being joined. For more details on the rowset source see U-SQL SELECT [FROM Clause](from-clause-u-sql.md).  
  
- <a name="row_src"></a>**`Cross_Join_Operator`**  
The cross join operator joins the two rowsets by combining each row on the left side with each row on the right side.  
  
  <table><th>Syntax</th><tr><td><pre>
  Cross_Join_Operator :=                                                                              
       'CROSS' [<a href="join-hints.md">Parallel_Join_Hint</a>] 'JOIN'.
  </pre></td></tr></table>
      
  It allows the optional specification of a join hint. See [Join Hints](join-hints.md) for more details.  
  
- <a name="join_op"></a>**`Join_Operator`**  
  Specifies the join operation.
       
  <table><th>Syntax</th><tr><td><pre>
  Join_Operator :=                                                                                    
       <a href="#join_pre">[Join_Prefix]</a> <a href="#join_hnt">Join_Hints</a> 'JOIN'
  |    ['LEFT' | 'RIGHT'] <a href="#join_hnt">Join_Hints</a> <a href="#semi_join_op">Semijoin_Operator</a>.<br />
  <a href="#join_pre">Join_Prefix</a> :=
       'INNER'
  |    [['LEFT' | 'RIGHT' | 'FULL'] 'OUTER'].<br />
  <a href="#semi_join_op">Semijoin_Operator</a> :=
        '<a href="semijoin-u-sql.md">SEMIJOIN</a>' | '<a href="antisemijoin-u-sql.md">ANTISEMIJOIN</a>'.
  </pre></td></tr></table>

  The join operators can either be a variety of joins or semijoins.
 
  - <a name="join_pre"></a>**`[Join_Prefix]`** **`'JOIN'`**  
    Specifies the type of join. `JOIN` defaults to `INNER JOIN`, `OUTER JOIN` defaults to `LEFT OUTER JOIN`. See the sections on joins for more details on each of the join expressions.  
  
  - **`['LEFT' | 'RIGHT']`** <a name="semi_join_op"></a>**`Semijoin_Operator`**   
    Specifies the type of semijoin. `SEMIJOIN` and `ANTISEMIJOIN` both default to `LEFT SEMIJOIN` and `LEFT ANTISEMIJOIN` respectively. See the sections on semijoins for more details on each of the semijoin expressions.  
  
  - <a name="join_hnt"></a>**`Join_Hints`**  
    The optional specification of join hints. See [Join Hints](join-hints.md) for more details.  
        
  It is highly recommended to always fully specify the join operator.  
  
- <a name="join_on_cl"></a>**`Join_On_Clause`**  
  Specifies the join comparison that is being used to identify which of the rows from each rowset will be joined.  
  
  <table><th>Syntax</th><tr><td><pre>
  Join_On_Clause :=                                                                                   
       'ON' Join_Comparison_Expression.
  </pre></td></tr></table>
  
  - **`Join_Comparison_Expression`**  
    Provides the join comparison. See [Join Comparisons](#joinComps) for more details.  

### Join Comparisons<a name="joinComps"></a>
U-SQL, like most scaled out Big Data Query languages that support joins, restricts the join comparison to equality comparisons between columns in the rowsets to be joined. If the column references are not unique across all the rowsets in the query, they have to be fully qualified with the rowset variable name, rowset name or specified alias.  
  
<table><th align="left">Syntax</th><tr><td><pre>
Join_Comparison_Expression :=                                                                            
     Join_Equality {'AND' Join_Equality}.<br />
Join_Equality :=  
     Column_Identifier '==' Column_Identifier.<br />
Column_Identifier :=  
     [(Rowset_Variable | <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>) '.']  
     <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></table>
  
There are however ways to still apply other join predicates. If one has a non-equality comparison or a more complex expression (such as a method invocation) in the comparison, one can move the comparison to the SELECT’s WHERE clause. Or the more complex expression can be placed in an earlier SELECT statement’s column and then that alias can be referred to in the join comparison.  
  
> [!TIP] 
> U-SQL decided to limit the ON clause to simple equality only and not perform the described rewrites to make it clear to the user that the more complex join predicates will negatively impact performance of the joins, since they will hinder the use of indices and other join optimizations.

### Examples
- The examples are designed for execution in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable.  

   ```sql
    @employees = 
        SELECT * FROM 
            ( VALUES
            (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
            (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
            (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
            (4, "Amy",    100, (int?)35000, new DateTime(1999,02,27)),
            (5, "Justin", 100, (int?)15000, new DateTime(2015,01,12)),
            (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
            (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
            (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
            (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
            (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14)),
            (11, "Ethan", 400, (int?)9000,  new DateTime(2015,08,22)),
            (12, "David", 800, (int?)100,   new DateTime(2016,11,01)),
            (13, "Andrew", 100, (int?)null, new DateTime(1995,07,16)),
            (14, "Jennie", 100, (int?)34000, new DateTime(2000,02,12))
            ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);
   ```

**A.    How to write U-SQL joins with equality and in-equality comparisons**  
The query first identifies a subset of data, `DeptID` and `DeptMaxSalary`, and stores it in a new rowset variable.  Then both rowset variables are joined on `DeptID` to identify all employees that have a salary that is lower than the highest salary in his/her dept.
```sql
@employees2 =
    SELECT DeptID,
           MAX(Salary) AS DeptMaxSalary
    FROM @employees
    GROUP BY DeptID;

@result =
    SELECT a.EmpName, a.DeptID, a.Salary, b.DeptMaxSalary
    FROM @employees AS a
         JOIN
             @employees2 AS b
         ON a.DeptID == b.DeptID
    WHERE a.Salary < b.DeptMaxSalary;

OUTPUT @result
TO "/Output/ReferenceGuide/Joins/exampleA.csv"
USING Outputters.Csv();
``` 

**B.    How to write U-SQL joins with non-equijoins.**    
Returns each employee, his/her salary, and the number of employees with a higher salary
```sql
@result =
    SELECT a.EmpName,
           a.Salary,
           COUNT( * ) - 1 AS NumberOfEmployeesWithHigherSalary
    FROM @employees AS a
         CROSS JOIN @employees AS b
    WHERE a.Salary <= b.Salary
    GROUP BY a.EmpName, a.Salary;

OUTPUT @result
TO "/Output/ReferenceGuide/Joins/exampleB.csv"
ORDER BY Salary DESC
USING Outputters.Csv();
```

**C.	How to write U-SQL joins where join comparison includes more complex expressions**   
All employees that have a salary that is equal to the adjusted highest salary in his/her dept.
```sql
@employees2 =
    SELECT DeptID,
           MAX(Salary)-1000 AS DeptAdjustedMaxSalary
    FROM @employees
    GROUP BY DeptID;

@result =
    SELECT a.EmpName, a.DeptID, a.Salary, b.DeptAdjustedMaxSalary
    FROM @employees AS a
         JOIN
             @employees2 AS b
         ON a.DeptID == b.DeptID AND a.Salary == b.DeptAdjustedMaxSalary;

OUTPUT @result
TO "/Output/ReferenceGuide/Joins/exampleC.csv"
USING Outputters.Csv();
```

**D.	How to write U-SQL joins where join comparison includes more complex expressions, additional example.**    
This query identifies departments that have more than three employees.  The expression is then joined back to the rowset variable to identify the employees from departments which have more than three employees.
```sql
@result =
    SELECT a.DeptID,
           a.EmpName
    FROM @employees AS a
         JOIN
         (
         SELECT DeptID
         FROM @employees
         GROUP BY DeptID
         HAVING COUNT( * ) > 3
         ) AS b
         ON a.DeptID == b.DeptID;

OUTPUT @result
TO "/Output/ReferenceGuide/Joins/exampleD.csv"
USING Outputters.Csv();
```

### See Also 
* [Data Modification Language (DML) Statements (U-SQL)](data-modification-language-dml-statements-u-sql.md)    
* [INNER JOIN (U-SQL)](inner-join-u-sql.md)
* [OUTER JOIN (U-SQL)](outer-join-u-sql.md)
* [CROSS JOIN (U-SQL)](cross-join-u-sql.md)
* [SEMIJOIN (U-SQL)](semijoin-u-sql.md)
* [ANTISEMIJOIN (U-SQL)](antisemijoin-u-sql.md)
* [Join Hints](join-hints.md)

