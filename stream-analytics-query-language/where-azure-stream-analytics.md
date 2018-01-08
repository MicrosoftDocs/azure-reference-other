---
title: "WHERE (Azure Stream Analytics) | Microsoft Docs"
ms.custom: ""
ms.date: "2016-04-22"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "stream-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
applies_to: 
  - "Azure"
ms.assetid: c9d48221-25d0-4a8c-9624-33561894bc1e
caps.latest.revision: 6
author: "SnehaGunda"
ms.author: "sngun"
manager: "jhubbard"
---
# WHERE (Azure Stream Analytics)
  Specifies the search condition for the rows returned by the query.  
  
 **Syntax**  
  
```  
[ WHERE <search_condition> ]  
  
<search_condition> ::=   
    { [ NOT ] <predicate> | ( <search_condition> ) }   
    [ { AND | OR } [ NOT ] { <predicate> | ( <search_condition> ) } ]   
[ ,...n ]   
<predicate> ::=   
    { expression { = | < > | ! = | > | > = | ! > | < | < = | ! < } expression   
    | string_expression [ NOT ] LIKE string_expression   
    | expression [ NOT ] BETWEEN expression AND expression   
    | expression IS [ NOT ] NULL }  
  
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
  
 **[NOT] NULL**  
  
 Specifies a search for null values, or for values that are not null, depending on the keywords used.  
  
## Example  
  
```  
SELECT TollId, EntryTime, VehicleType, LicensePlate, Toll, Tag  
FROM TollTagEntry TIMESTAMP BY EntryTime  
WHERE ( CAST(TollId AS bigint) BETWEEN 1 AND 2 )  
AND LicensePlate LIKE '%AC%'  
  
```  
  
  