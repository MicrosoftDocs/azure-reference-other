---
title: "RAISE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2018-05-18"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# RAISE (U-SQL)
Generates compile-time errors and/or warnings.

## Syntax
<pre>
RAISE_Statement :=
    'RAISE' ('<a href="#err">ERROR</a>' | '<a href="#war">WARNING</a>') <a href="#sse">Static_String_Expression</a>.
</pre>


## Semantics of Syntax Elements  
- <a name="err"></a>**`ERROR`**  
Raises a compile time error `E_CSC_USER_RAISEERROR` of the form:
  ```
  DESCRIPTION: The user script raised a user defined error.
  MESSAGE: RAISE ERROR: _the provided error message_
  ```

- <a name="war"></a>**`WARNING`**  
Raises a compile time warning `W_CSC_USER_RAISEWARNING` of the form:
  ```
  DESCRIPTION: The user script raised a user defined warning.
  MESSAGE: RAISE ERROR: _the provided warning message_
  ```

- <a name="sse"></a>**`Static_String_Expression`**  
Provides the error/warning message. If the expression evaluates to `null`, an error is raised.

> [!IMPORTANT]  
> Currently, warnings are  not passed through to the front-end APIs or tooling.

## Examples
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  


**Basic Example**  
The following script will raise an error if a file does not exists or if it contains some data and it will raise a warning if the output file already exists.
```sql
DECLARE @semfile = @"/output/releasenotes/winter2018/raise-error-warning_sem.txt";
DECLARE @outfile = @"/output/releasenotes/winter2018/raise-error-warning_out.csv";

DECLARE @error = "Semaphore file <" + @semfile +"> does not exists or is locking the job. Job aborted.";
DECLARE @warning = "Output file <{0}> already exists and will be overwritten.";

IF (!FILE.EXISTS(@semfile) || FILE.LENGTH(@semfile) > 0) THEN
   RAISE ERROR @error;
ELSEIF (FILE.EXISTS(@outfile)) THEN
   RAISE WARNING String.Format(@warning, @outfile);
END;

@data = SELECT "This is some data" AS data FROM (VALUES(1)) AS T(x);

OUTPUT @data
TO @outfile
USING Outputters.Csv();

OUTPUT (SELECT x FROM (VALUES(1)) AS T(x) WHERE false) 
TO @semfile
USING Outputters.Csv();
```


## See Also 
* [U-SQL Scripts](u-sql-scripts.md)  
* [IF...ELSE (U-SQL)](if-else-u-sql.md)  
