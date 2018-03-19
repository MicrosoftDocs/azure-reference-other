---
title: "Other Simple Built-In Types and Literals | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 77189ada-7641-44a7-a0aa-f0ee8629abfd
caps.latest.revision: 4
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# Other Simple Built-In Types and Literals
U-SQL’s also supports the following simple built-in types:  
```
bool       bool?  
Guid       Guid?  
byte[]  
```
The grammar rules use `Other_Type` to refer to one of these types.  
  
The maximal size of a column of type `byte[]` is the same as the maximal size of a row which currently is 4MB.  
  
The built-in type `bool` uses the standard C# literals `true` and `false`.  
  
The built-in type `Guid` does not have a built-in literal form, but requires the standard C# construction mechanisms such as `Guid.Parse()` or new `Guid()`. Note that these constructions with simple string parameters are constant folded (executed at compile time) and thus are similar to a built-in literal.  
  
The built-in type `byte[]` does not have a built-in literal form, but accepts the standard C# construction `new byte[] {}` as a constant-foldable constructor.  

### See Also
* [Simple Built-In U-SQL Types](simple-built-in-u-sql-types.md)
* [Data Types and Literals (U-SQL)](data-types-and-literals-u-sql.md)  

  