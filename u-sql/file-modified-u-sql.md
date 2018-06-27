---
title: "FILE.MODIFIED (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 057567b4-8651-438f-bbca-c62cd1e5d010
caps.latest.revision: 4
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# FILE.MODIFIED (U-SQL)
Returns the last modified timestamp of the file at the specified location at compile time as a DateTime value (Kind is `Unspecified`). 

## Syntax
<pre>
<a href="temporal-types-and-literals.md">DateTime?</a> MODIFIED(
    <a href="textual-types-and-literals.md">string</a> <a href="#path">path</a>
). 
</pre>

## Parameters
- <a name="path"></a>**`path`**   
A constant-foldable string expression.  `path` can be any supported file path Universal Resource Identifier (URI).  If `path` is not constant-foldable, the error `E_CSC_USER_EXPRESSIONNOTCONSTANTFOLDABLE` is raised.  If `path` is empty (null or the zero-length string), the error `E_CSC_USER_EMPTYFILEPATH` is raised. If `path` contains invalid characters, the error `E_CSC_USER_INVALIDFILENAME` is raised.

## Return Value
[DateTime?](temporal-types-and-literals.md)   
The last modified timestamp of `path` at compile time as a DateTime value (Kind is Unspecified).  `Null` if `path` does not exists, refers to a folder or the user has no access to it. 

## Example
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).   
- `SearchLog.tsv` is available @ https://github.com/Azure/usql/blob/master/Examples/Samples/Data/SearchLog.tsv.  


```sql
DECLARE @filepath_good = "/Samples/Data/SearchLog.tsv";
DECLARE @filepath_bad = "/Samples/Data/zzz.tsv";
 
@result =
    SELECT  FILE.MODIFIED(@filepath_good) AS modified_datetime_good,
            FILE.MODIFIED(@filepath_bad) AS modified_datetime_bad
    FROM (VALUES (1)) AS T(dummy);
 
OUTPUT @result
TO "/ReferenceGuide/BuiltInFunctions/MetadataFunctions/FileModified.txt"
USING Outputters.Csv();
```

## See Also
* [FILE Functions (U-SQL)](file-functions-u-sql.md)
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [C# Functions and Operators (U-SQL)](csharp-functions-and-operators-u-sql.md)

