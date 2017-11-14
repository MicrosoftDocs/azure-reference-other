---
title: "U-SQL Syntax Conventions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: c9ac5833-5029-477c-a844-8bb9fdd88532
caps.latest.revision: 5
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Syntax Conventions (U-SQL)
This document uses an [Extended Backus-Naur syntax](http://matt.might.net/articles/grammars-bnf-ebnf/) notation of the following structure:  
  
Each syntax grammar rule has a `name` followed by the `rule` body, as in:  
```  
name := rule.  
```  
Each `rule` body is either a reference to a `name` or a composition of the following rule expressions recursively.  The following table lists and describes conventions that are used in the syntax diagrams in the U-SQL Language Reference. 

|Convention|Used for|
|------|------|
|UPPERCASE|U-SQL keywords.|
|`[rule]`|Brakets indicate that the grammar `rule` rule occurs either 0 or 1 times. Do not type the brackets.|
|`{rule}`|Curly braces indicate that the grammar rule `rule` occurs 0 to n times.  Do not type the braces.|
|`(rule)`|Parenthesis are used to nest and group grammar rules. Do not type the parenthesis.|
|`rule1` &#124; `rule2`|The vertical line represents a choice between `rule1` or `rule2`. It binds weaker than any of the other grammar rules.  You can use only one of the items.|
|`'abc'`|Literal keyword `abc`.|
|`'abc'+rule`|Literal prefix `abc` tied to result of grammar rule `rule` without optional whitespace. |
|;|U-SQL statement terminator.|
  
Upper-case rule names inside a rule definition are defined in the language reference documentation. Lower-case rule names are considered self-evident and not further specified.  
  
### See Also
* [Securing Meta Data Objects](securing-meta-data-objects.md)
* [Language Elements (U-SQL)](language-elements-u-sql.md)

