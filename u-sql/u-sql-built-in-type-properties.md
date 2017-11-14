---
title: "U-SQL Built-in Type Properties | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 402d8a7c-2395-4c73-8a14-eea4c05739fb
caps.latest.revision: 6
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Built-in Type Properties
Each of the U-SQL built-in types have certain properties that will govern its usability in certain context.  
  
For example, the [numeric types](numeric-types-and-literals.md) are orderable, while [complex types](complex-built-in-u-sql-types.md) are not orderable. As one would expect, this means that an expression that results in a complex type cannot be used in an [ORDER BY](order-by-and-offset-fetch-clause-u-sql.md) clause, while any expression that results in an orderable type can.  
  
### See Also
* [Data Types and Literals (U-SQL)](data-types-and-literals-u-sql.md) 
