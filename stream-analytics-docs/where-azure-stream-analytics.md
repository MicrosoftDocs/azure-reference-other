---
title: "WHERE (Azure Stream Analytics)"
description: "Specifies the search condition for the rows returned by the query. "
applies_to:
  - "Azure"


ms.service: azure-stream-analytics
ms.topic: reference
ms.date: 08/02/2024
---
# WHERE (Azure Stream Analytics)
  Specifies the search condition for the rows returned by the query.

 ## Syntax

```SQL
[ WHERE <search_condition> ]

<search_condition> ::=
    { [ NOT ] <predicate> | ( <search_condition> ) }
    [ { AND | OR } [ NOT ] { <predicate> | ( <search_condition> ) } ]
[ ,...n ]
<predicate> ::=
    { expression { = | < > | ! = | > | > = | ! > | < | < = | ! < } expression
    | string_expression [ NOT ] LIKE string_expression
    | expression [ NOT ] BETWEEN expression AND expression
    | expression IS [ NOT ] NULL
    | expression [ NOT ] IN ( expression [ ,...n ] )
    }

```

## Arguments
 **\< search_condition >**

 Specifies the conditions for the rows returned in the result set for a SELECT statement, query expression, or subquery. There is no limit to the number of predicates that can be included in a search condition.

 **NOT**

 Negates the Boolean expression specified by the predicate.

 **AND**

 Combines two conditions and evaluates to TRUE when both of the conditions are TRUE.

 **OR**

 Combines two conditions and evaluates to TRUE when either condition is TRUE.

 **\< predicate >**

 Is an expression that returns TRUE or FALSE.

 **expression**

 Is a column name, a constant, a function, a variable, a scalar subquery, or any combination of column names, constants, and functions connected by an operator or operators, or a subquery. The expression can also contain the CASE expression.

 **=**

 Is the operator used to test the equality between two expressions.

 **<>**

 Is the operator used to test the condition of two expressions not being equal to each other.

 **!=**

 Is the operator used to test the condition of two expressions not being equal to each other.

 **>**

 Is the operator used to test the condition of one expression being greater than the other.

 **>=**

 Is the operator used to test the condition of one expression being greater than or equal to the other expression.

 **!>**

 Is the operator used to test the condition of one expression not being greater than the other expression.

 **<**

 Is the operator used to test the condition of one expression being less than the other.

 **<=**

 Is the operator used to test the condition of one expression being less than or equal to the other expression.

 **!<**

 Is the operator used to test the condition of one expression not being less than the other expression.

 **String_expression**

 Is a string of characters and wildcard characters.

 **[NOT] LIKE**

 Indicates that the subsequent character string is to be used with pattern matching.

 **[NOT] BETWEEN**

 Specifies an inclusive range of values. Use AND to separate the starting and ending values.

 **IS [NOT] NULL**

 Specifies a search for null values, or for values that are not null, depending on the keywords used.
 To determine whether an expression is NULL, use IS NULL or IS NOT NULL instead of comparison operators (such as = or !=). Comparison operators return false when either or both arguments are NULL.
For example both `col1 = 1` and `col1 != 1` are false when col1 value is NULL, while `col1 IS NULL` is true in that case.

 **[NOT] IN**

 Specifies a list of values. Expect a list of comma separated values between parenthesis : `('a','b','c')`

## Example

```SQL
SELECT TollId, EntryTime, VehicleType, LicensePlate, Toll, Tag
FROM TollTagEntry TIMESTAMP BY EntryTime
WHERE ( CAST(TollId AS bigint) BETWEEN 1 AND 2 )
AND LicensePlate LIKE '%AC%'

```
