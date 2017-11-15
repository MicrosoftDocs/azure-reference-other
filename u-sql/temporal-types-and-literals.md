---
title: "Temporal Types and Literals | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 37a983a3-8584-45ee-83b9-55efb6dc1f62
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Temporal Types and Literals
U-SQL’s built-in temporal types are:  
```
DateTime   DateTime?  
```
The grammar rules use `Temporal_Type` to refer to one of these types.  
  
U-SQL’s temporal types do not have a built-in literal form, but require the standard C# construction mechanisms such as [DateTime.Parse()](https://msdn.microsoft.com/library/system.datetime.parse(v=vs.110).aspx) or [new DateTime()](https://msdn.microsoft.com/library/system.datetime.datetime(v=vs.110).aspx). Note that these constructions with simple string and number parameters are constant folded (executed at compile time) and thus are similar to a built-in literal.  
  
### See Also
* [Simple Built-In U-SQL Types](../u-sql/simple-built-in-u-sql-types.md)
* [Data Types and Literals (U-SQL)](../u-sql/data-types-and-literals-u-sql.md)  
* [Date & Time](../u-sql/csharp-functions-and-operators-u-sql.md#DateTime)
