---
title: "Aggregate Functions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 51cd2509-5db8-4a5f-8f5b-5461782a928a
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Aggregate Functions (U-SQL)
U-SQL provides both built-in aggregation functions and the ability for the user to define [user-defined aggregators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg).  

An aggregator will compute a single result value over a group of values and will have an identity value for the case that the group is empty. 

In U-SQL, aggregators can only be used in the following syntactic contexts: 

* Inside a SELECT’s SELECT clause:
  * It will calculate the aggregated value for each group specified by a [GROUP BY](group-by-and-having-clauses-u-sql.md) clause. If the rowset is empty and thus all groups are empty, the [SELECT](select-expression-u-sql.md) expression will return an empty rowset. 

  * If no [GROUP BY](group-by-and-having-clauses-u-sql.md) has been specified, then every column in the SELECT clause has to be an expression that needs to contain at least one aggregator. The aggregations will be computed across the whole rowset of the SELECT expression. If the rowset is empty, then the aggregators return their identity value, which is the value that is would not change the aggregation result if it was added. I.e., 0 for [COUNT()](count-u-sql.md) and null for all others.

  * As part of a [U-SQL windowing expression](over-expression-u-sql.md) where it will calculate the aggregated value inside each window partition. Some built-in aggregators are not supported in windowing expressions (see each aggregator section for more details). 

  * Aggregations can appear in expressions 

  * Aggregations always need to be aliased in the [SELECT](select-expression-u-sql.md) clause. 
  
* Inside a [GROUP BY’s HAVING](group-by-and-having-clauses-u-sql.md) clause to provide a filter condition on the group based on the aggregation’s value. 
 
Some of the aggregators are type-polymorphic, meaning that they can operate on many different input types and return potentially different types based on their input type. For example, [COUNT](count-u-sql.md)() will take any input type, and always return a value of type [long](numeric-types-and-literals.md), while [SUM](sum-u-sql.md)() will return a value of a type that is dependent on the input type: [SUM](sum-u-sql.md)(v) where v is of type [double](numeric-types-and-literals.md) will return a result of type [double](numeric-types-and-literals.md); if v is an integral numeric type such as [int](numeric-types-and-literals.md), the result will be of type [long](numeric-types-and-literals.md). 

Several aggregators can be used in the same SELECT clause and will be applied on the groups. 

Aggregators cannot be nested. 

<table><th align="left">Syntax</th><tr><td><pre>
Aggregate_Expression :=                                                                                  
      <a href="#aggr">Aggregator</a> '(' ['<a href="#dist">DISTINCT</a>'] <a href="#exp">expression</a> ')'. 
</pre></td></tr></table>

### Semantics of Syntax Elements 
* <a name="dist"></a>**`DISTINCT`**  
Every aggregator can take an optional DISTINCT qualifier that will de-duplicate the values in the group before performing the aggregation. The data type of the values will have to be comparable if DISTINCT is being used. DISTINCT is not allowed when the aggregator is being used in an [OVER](over-expression-u-sql.md) expression.

* <a name="aggr"></a>**`Aggregator`**  
Can be either the invocation of a [user-defined aggregator](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg) or a built-in aggregator: 

  <table><th>Syntax</th><tr><td><pre>Aggregator :=                                                                                       <br />     <a href="https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg">User_Defined_Aggregator</a> | Built_In_Aggregator.</pre></td></tr></table>


  U-SQL provides the following built-in aggregation functions (follow the links for more information): 

  <table><th>Syntax</th><tr><td><pre>Built_In_Aggregator :=                                                                              <br />      <a href="any-value-u-sql.md">'ANY_VALUE'</a>
  |     <a href="array-agg-u-sql.md">'ARRAY_AGG'</a>
  |     <a href="avg-u-sql.md">'AVG'</a>
  |     <a href="count-u-sql.md">'COUNT'</a>
  |     <a href="map-agg-u-sql.md">'MAP_AGG'</a>
  |     <a href="max-u-sql.md">'MAX'</a>
  |     <a href="min-u-sql.md">'MIN'</a>
  |     <a href="sum-u-sql.md">'SUM'</a>
  |     <a href="stdev-u-sql.md">'STDEV'</a>
  |     <a href="stdevp-u-sql.md">'STDEVP'</a>
  |     <a href="var-u-sql.md">'VAR'</a>
  |     <a href="varp-u-sql.md">'VARP'</a>.</pre></td></tr></table>



* <a name="exp"></a>**`expression`**  
The C# expression (including column references) that gets aggregated. The expression cannot contain other aggregators. Some aggregators may support additional options besides 

### See also 
* [OVER Expression (U-SQL)](over-expression-u-sql.md) 
* [GROUP BY and HAVING Clauses (U-SQL)](group-by-and-having-clauses-u-sql.md)
* [SELECT Expression (U-SQL)](select-expression-u-sql.md)
* [U-SQL Programmability Guide: User-Defined Aggregators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)  
