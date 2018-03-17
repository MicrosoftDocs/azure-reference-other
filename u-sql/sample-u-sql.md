---
title: "SAMPLE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/14/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a48c1658-64fa-48c2-8e06-bb70bc81d368
caps.latest.revision: 13
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# SAMPLE (U-SQL)
U-SQL supports samplers natively. The `SAMPLE` clause enables convenient access from within a `SELECT` expression.  All samplers execute in one pass on data and in parallel on portions of the input; they do not require partitioning, shuffle etc. 	Samplers have been implemented in a single pass over data and have very small memory footprint; log( SIZE(input), SIZE(output) ).

<table><th align="left">Syntax</th><tr><td><pre>
Sample_Expression_Simple :=                                                                              
     <a href="query-statements-and-expressions-u-sql.md">Query_Expression</a> 'SAMPLE' ( '<a href="#any">ANY</a>' '(' <a href="#row_count">row_count</a> ')' | '<a href="#uniform">UNIFORM</a>' '(' <a href="#row_fraction">row_fraction</a> ')' ).
</pre></td></tr></table>

### Semantics of Syntax Elements    
-  <a name="any"></a>**`ANY`**  
*Any* `row_count` rows from the input rowset.  `ANY` does not return a randomly chosen subset of rows; do not use where randomness is needed.

- <a name="row_count"></a>**`row_count`**  
A positive integer.

- <a name="uniform"></a>**`UNIFORM`**  
Rows are picked uniformly at random with probability equal to `row_fraction`.  The size of the output is governed by a binomial distribution. In expectation, the size of output is `row_fraction` * SIZE(input rowset).

- <a name="row_fraction"></a>**`row_fraction`**  
A double between 0 and 1 that indicates the probability with which a row in the input rowset will be passed.

> [!TIP] 
> Ensure your sample probability, `row_fraction`, is adequate for the size of your dataset to minimize the possibility of an empty result set being returned.

### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable, `@data`.  

**Dataset**   
```sql
@data = 
    SELECT * FROM 
        ( VALUES
        ("02143",   30,     100,  "Smith"),
        ("98052",   25,     50,   "Andersen"),
        ("02139",   30,     75,   "Todd"),
        ("02139",   25,     60,   "Roberts"),
        ("61801",   23,     80,   "Sanders")
        ) AS T(ZipCode, Age, Salary, LastName);
```
--------------------------------------------------

**ANY**  
Samples the `@data` rowset by selecting the specified number of rows (2) in a completely arbitrary way.
```sql
@result = 
    SELECT * FROM @data SAMPLE ANY (2);

OUTPUT @result
TO "/ReferenceGuide/QSE/Sample/any.txt"
USING Outputters.Tsv();
```
Possible output below. 

ZipCode  |Age      |Salary   |LastName   
---------|---------|---------|---------  
02143    |30       |100      |Smith    
98052    |25       |50       |Andersen 
--------------------------------------------------
 
**UNIFORM**   
Samples the `@data` rowset using a random uniform sampling with the provided probability (10%).
```sql
@result =
    SELECT * FROM @data SAMPLE UNIFORM (0.1);

OUTPUT @result
TO "/ReferenceGuide/QSE/Sample/simple_uniform.txt"
USING Outputters.Tsv();
```
Possible output below.  The likelihood of this output is 0.00729 (two rows are picked with a probability of 0.1 each and three rows not picked with a probability of 0.9 each).  Note: An empty result set may be returned in this example due to the low probability and small dataset.

ZipCode  |Age      |Salary   |LastName   
---------|---------|---------|---------  
02143    |30       |100      |Smith    
98052    |25       |50       |Andersen 
--------------------------------------------------



### See Also
* [SAMPLE Expression (U-SQL)](sample-expression-u-sql.md) 
* [U-SQL Sampling Methods](u-sql-sampling-methods.md) 
* [Operators (U-SQL)](operators-u-sql.md)
