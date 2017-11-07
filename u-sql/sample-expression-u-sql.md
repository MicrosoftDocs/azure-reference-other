---
title: "SAMPLE Expression (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-14"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cd5ba00f-6771-4c16-b753-7091a7172710
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# SAMPLE Expression (U-SQL)
USQL supports samplers natively. The sample expression is needed to access some types of samplers. 

Given an input rowset and arguments that are specific to the types of sampler being invoked, the sample expression outputs a rowset that is a statistical sample of the input.  Moreover, the sample expression takes as input an optional identifier (column) that records the probability with which the corresponding row has been output.

All samplers execute in one pass on data and in parallel on portions of the input; they do not require partitioning, shuffle etc.  Samplers have been implemented in a single pass over data and have very small memory footprint; log( SIZE(input), SIZE(output) ).

<table><th>Syntax</th><tr><td><pre>
Sample_Expression_Complex :=                                                                             
    'SAMPLE' <a href="from-clause-u-sql.md#row_src">Rowset_Source</a> Sampler_Details [Weight_Col]<br />
Sampler_Details := 
<a></a>    '<a href="#uniform">UNIFORM</a>' '(' <a href="#row_fraction">row_fraction</a> ')'
|   'ON' <a href="#ON">Identifier_List</a> '<a href="#universe">UNIVERSE</a>' '(' <a href="#row_fraction">row_fraction</a> ')'
|   'ON' <a href="#ON">Identifier_List</a> '<a href="#distinct">DISTINCT</a>' '(' <a href="#row_fraction">row_fraction</a> ',' <a href="#min_row_count">min_row_count</a> ')'<br />
Weight_Col :=
<a></a>    'WITH' 'WEIGHT' 'AS' Identifier.
</pre></td></tr></table>


### Semantics of Syntax Elements   
-   <a name="uniform"></a>**`UNIFORM`**  
Rows are picked uniformly at random with probability equal to `row_fraction`.  The weight column, if requested, is set to 1/(`row_fraction`) for all rows.  The size of the output is governed by a binomial distribution. In expectation, the size of output is `row_fraction` * SIZE(input rowset).
 
-   <a name="row_fraction"></a>**`row_fraction`**  
A double between 0 and 1 that indicates the probability with which a row in the input rowset will be passed.

- <a name="ON"></a>**`Identifier_List`**   
  This option specifies the list of columns that define the groups.  
  
  <table><th>Syntax</th><tr><td><pre>
Identifier_List :=                                                                                  
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>                                               
    {',' <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a> }.  
</pre></td></tr></table> 

-   <a name="universe"></a>**`UNIVERSE`**  
All rows are passed where the group value (i.e., the value of the columns in `Identifier_List`) is in some randomly chosen `row_fraction` of the space of group values. `UNIVERSE` uses a cryptographically strong hash function to pick a random portion of the values. The weight column, if requested, is set to 1/(`row_fraction`) for all rows.  

    `UNIVERSE` ensures sample-then-join is equivalent to join-then-sample: Using `UNIVERSE` before an equijoin with `Identifier_List`, on both inputs of the equijoin, containing exactly the equijoin columns is identical to sampling after the join.
    
    The size of the output is also in expectation `row_fraction`*SIZE(input rowset). However, especially if there are too few groups, the output size has more variance than with `UNIFORM` since all rows from a group are passed by the sampler or not.  

-   <a name="distinct"></a>**`DISTINCT`**  
Per group (a distinct value of the columns in `Identifier_List`), this sampler passes `min_row_count` rows and the rest of the rows are passed with probability `row_fraction`.  The weight column, if requested, is set to 1/(`row_fraction`) if the row is passed in the probabilistic mode and 1 otherwise.  `DISTINCT` facilitates sample-before-groupby: Using `DISTINCT` before a groupby, with `Identifier_List` containing at least the group in the group-by, guarantees that the sample will not miss any groups.

    `DISTINCT` may return fewer than `min_row_count` rows (but never less than 1) for some groups. A simple case is when a group has fewer than `min_row_count` rows in the input. A more complex case occurs depending on the degree of parallelism of the stage that runs the sampler and how the rows corresponding to the group are distributed among the input partitions. 

-   <a name="min_row_count"></a>**`min_row_count`**  
A positive integer for  `DISTINCT`.

> [!TIP] 
> Ensure your sample probability, `row_fraction`, is adequate for the size of your dataset to minimize the possibility of an empty result set being returned.


### Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.
- The examples below are based on the dataset defined below.  Ensure your execution includes the rowset variable, `@data`.  

**Dataset**   
```
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

**UNIFORM**  
```
@result = 
    SAMPLE @data UNIFORM (0.4) WITH WEIGHT AS _Weight;

OUTPUT @result
TO "/ReferenceGuide/QSE/Sample/uniform.txt"
USING Outputters.Tsv();
```
Possible output below.  Note that the output need not contain every `ZipCode` or all rows that have a given `Age` value.  The likelihood of seeing this output is 0.03456.

ZipCode  |Age      |Salary   |LastName |Weight  
---------|---------|---------|---------|---------  
02143    |30       |100      |Smith    |2.5
98052    |25       |50       |Andersen |2.5 
--------------------------------------------------

**UNIVERSE**  
Samples the `@data` rowset by picking some randomly chosen fraction of the overall value-space of the ON columns and returning all rows whose value of the ON columns belongs in the chosen space. The query implicitly picks 10% of all the values of the `Age` columns and returns all rows whose value of `Age` was randomly chosen. 
```
@result = 
    SAMPLE @data ON Age UNIVERSE (0.1);

OUTPUT @result
TO "/ReferenceGuide/QSE/Sample/universe.txt"
USING Outputters.Tsv();
```
Possible output below.  Note that all rows with `Age`=30 will be picked if any of the `Age`=30 rows are picked. Similar all rows with `Age`=25 will either be picked or not be picked (as in this example). 

The likelihood of seeing this output is 0.081; this is one of the three outcomes that have the same probability after no-output which occurs with a likelihood of 0.729 since there are only three unique values for `Age`.  Note: An empty result set may be returned in this example due to the low probability and small dataset.

ZipCode  |Age      |Salary   |LastName  
---------|---------|---------|--------- 
02143    |30       |100      |Smith    
02139    |30       |75       |Todd 
--------------------------------------------------


**DISTINCT**  
Samples the `@data` rowset such that at least 3 rows per distinct value of the `ZipCode` column are included, and additional rows are added with the indicated probability (10%). The weight of each passing row is added to the resulting rowset in the weight column `_Weight`. 
```
@result = 
    SAMPLE @data ON ZipCode DISTINCT (0.1, 3) WITH WEIGHT AS _Weight;

OUTPUT @result
TO "/ReferenceGuide/QSE/Sample/distinct.txt"
USING Outputters.Tsv();
```
Possible output below.  Note that every `ZipCode` is represented in the output by up to 3 rows, if as many rows are available in the input. The likelihood of seeing this output is 1.

ZipCode  |Age      |Salary   |LastName |Weight  
---------|---------|---------|---------|---------  
02143    |30       |100      |Smith    |1
98052    |25       |50       |Andersen |1 
02139    |30       |75       |Todd     |1
02139    |25       |60       |Roberts  |1 
61801    |23       |80       |Sanders  |1 
--------------------------------------------------


### See Also
* [SAMPLE (U-SQL)](../USQL/sample-u-sql.md)
* [U-SQL Sampling Methods](../USQL/u-sql-sampling-methods.md)  
* [FROM Clause (U-SQL)](../USQL/from-clause-u-sql.md) 