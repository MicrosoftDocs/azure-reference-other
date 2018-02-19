---
title: "FILE.LENGTH (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 4b639131-561e-41eb-b0e5-e9d24db6c860
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# FILE.LENGTH (U-SQL)
Returns the logical size in bytes of the file at the specified location at compile time.

<table><th align="left">Syntax</th><tr><td><pre>
<a href="numeric-types-and-literals.md">long?</a> LENGTH(
    <a href="textual-types-and-literals.md">string</a> <a href="#path">path</a>
).                                                                                                       
</pre></td></tr></table>

### Parameters
-   <a name="path"></a>**`path`**   
A constant-foldable string expression.  `path` can be any supported file path Universal Resource Identifier (URI).  If `path` is not constant-foldable, the error `E_CSC_USER_EXPRESSIONNOTCONSTANTFOLDABLE` is raised.  If `path` is empty (null or the zero-length string), the error `E_CSC_USER_EMPTYFILEPATH` is raised. If `path` contains invalid characters, the error `E_CSC_USER_INVALIDFILENAME` is raised.

### Return Value
[long?](numeric-types-and-literals.md)   
The logical size in bytes of `path` at compile time.  `Null` if `path` does not exists, refers to a folder or the user has no access to it. 

### Example
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The example below uses the sample data provided with your Data Lake Analytics account. See [Prepare source data](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal#prepare-source-data) for additional information.

```sql
DECLARE @filepath_good = "/Samples/Data/SearchLog.tsv";
DECLARE @filepath_bad = "/Samples/Data/zzz.tsv";
 
@result =
    SELECT  FILE.LENGTH(@filepath_good) AS length_good,
            FILE.LENGTH(@filepath_bad) AS length_bad
    FROM (VALUES (1)) AS T(dummy);
 
OUTPUT @result
TO "/Output/ReferenceGuide/BuiltInFunctions/SystemFunctions/FileLength.txt"
USING Outputters.Csv();
```

### See Also
* [FILE Functions (U-SQL)](file-functions-u-sql.md)
* [Built-in Functions (U-SQL)](built-in-functions-u-sql.md) 
* [C# Functions and Operators (U-SQL)](csharp-functions-and-operators-u-sql.md)


