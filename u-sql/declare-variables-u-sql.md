---
title: "DECLARE Variables (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "09/28/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f11c4bbb-51ac-4f9c-a429-d96018118681
caps.latest.revision: 2
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---
# DECLARE Variables (U-SQL)
The DECLARE statement initializes a U-SQL variable.

<table><th align="left">Syntax</th><tr><td><pre>
Variable :=                                                                                              
    System_Variable | User_Variable.<br />
System_Variable := '@@'+Name.<br />
User_Variable := "@"+<a href="u-sql-identifiers.md">Unquoted_Identifier</a>.
</pre></td></tr></table>

Variables allow you to name scalar and rowset expressions. A simple example should illustrate how this works:  
  
```sql  
DECLARE @city string = "Seattle";  
```  
  
You can do more than store simple values. You can use C# Expressions to compute values  
  
```sql  
DECLARE @city string = "Seat" + "tle";  
```  
  
You can even call limited set of methods that can be constant-folded.  
  
```sql  
DECLARE @city string = ("Seat"+ "tle").ToUpper();  
```  

Custom assembly objects, such as c# [user-defined functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf), can be referenced inside a DECLARE statement.
```sql
REFERENCE ASSEMBLY myassembly;

DECLARE @myvar string = "string "+myns.myclass.mystringfn();
```



**DECLARE EXTERNAL**   
`DECLARE EXTERNAL` allows the declaration of a script scalar expression variable that can be overwritten by a previous DECLARE statement without failing compilation.

For example, the following script will produce the specified file with content "external declaration":
```sql
DECLARE EXTERNAL @value string = "external declaration";

@r = SELECT * FROM (VALUES(@value)) AS T(x);
OUTPUT @r TO "/output/test.csv" USING Outputters.Csv();
```

The following script on the other hand will produce the file with the content "overwritten declaration".  This allows users to parameterize scripts with a default and allows tools (such as Azure Data Factory) to provide a parameter model and overwrite the default parameter values.
```sql
DECLARE @value string = "overwritten declaration";
DECLARE EXTERNAL @value string = "external declaration";

@r = SELECT * FROM (VALUES(@value)) AS T(x);
OUTPUT @r TO "/output/test.csv" USING Outputters.Csv();
```

**Differences from T-SQL**    
Unlike [T-SQL](https://msdn.microsoft.com/library/ms188927.aspx), a variable must be declared and initialized in the same statement.  In addition, SET cannot be used to update user variables.  You must DECLARE a new variable instead of using SET to update an existing one.	For example:
```sql
// Will fail
DECLARE @var string;

// Will also fail
DECLARE @var string = "";
SET @var = "a value"
```

## See Also
* [Using Variables (U-SQL)](using-variables-u-sql.md)
