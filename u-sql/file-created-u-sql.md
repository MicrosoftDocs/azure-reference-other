---
title: "FILE.CREATED (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: e5961285-13dc-4183-8bd2-96ef0fb37cae
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# FILE.CREATED (U-SQL)
Returns the creation timestamp of the file at the specified location at compile time as a DateTime value (Kind is `Unspecified`).

<table><th align="left">Syntax</th><tr><td><pre>
<a href="temporal-types-and-literals.md">DateTime?</a> CREATED(
    <a href="textual-types-and-literals.md">string</a> <a href="#path">path</a>
).                                                                                                       
</pre></td></tr></table>

### Parameters
-   <a name="path"></a>**`path`**   
A constant-foldable string expression.  `path` can be any supported file path Universal Resource Identifier (URI).  If `path` is not constant-foldable, the error `E_CSC_USER_EXPRESSIONNOTCONSTANTFOLDABLE` is raised.  If `path` is empty (null or the zero-length string), the error `E_CSC_USER_EMPTYFILEPATH` is raised. If `path` contains invalid characters, the error `E_CSC_USER_INVALIDFILENAME` is raised.

### Return Value
[DateTime?](temporal-types-and-literals.md)   
The creation timestamp of `path` at compile time as a DateTime value (Kind is Unspecified). `Null` if `path` does not exists, refers to a folder or the user has no access to it.

### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The example below uses the sample data provided with your Data Lake Analytics account. See [Prepare source data](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal#prepare-source-data) for additional information.

```
DECLARE @filepath_good = "/Samples/Data/SearchLog.tsv";
DECLARE @filepath_bad = "/Samples/Data/zzz.tsv";
 
@result =
    SELECT  FILE.CREATED(@filepath_good) AS created_datetime_good,
            FILE.CREATED(@filepath_bad) AS created_datetime_bad
    FROM (VALUES (1)) AS T(dummy);
 
OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/SystemFunctions/FileCreated.txt"
USING Outputters.Csv();
```

### See Also
* [FILE Functions (U-SQL)](file-functions-u-sql.md)
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md)  
* [C# Functions and Operators (U-SQL)](csharp-functions-and-operators-u-sql.md)

