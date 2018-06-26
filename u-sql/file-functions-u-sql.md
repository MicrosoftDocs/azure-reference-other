---
title: "FILE Functions (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "04/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 06838057-588a-44eb-963f-acdd3ec1629c
caps.latest.revision: 5
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# FILE Functions (U-SQL)
These intrinsic functions are currently always evaluated at compile time (and thus considered [constant-foldable](https://wikipedia.org/wiki/Constant_folding)). The functions can be called as part of any scalar expression.

## Functions
|Name   |Description|
|--|--|
|[CREATED(string)](file-created-u-sql.md)|Returns the creation timestamp of the file at the specified location at compile time as a DateTime value (Kind is `Unspecified`).|
|[EXISTS(string)](file-exists-u-sql.md)|Checks if a file in the specified location exists at compile time.|
|[LENGTH(string)](file-length-u-sql.md)|Returns the logical size in bytes of the file at the specified location at compile time.|
|[MODIFIED(string)](file-modified-u-sql.md)|Returns the last modified timestamp of the file at the specified location at compile time as a DateTime value (Kind is `Unspecified`). |
<br />

## See Also
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [C# Functions and Operators (U-SQL)](csharp-functions-and-operators-u-sql.md)

