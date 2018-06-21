---
title: "Output to Files (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 071f1a22-451f-4dc0-96da-8a979d4fe85c
caps.latest.revision: 11
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# Output to Files (U-SQL)
Currently U-SQL scripts are executed in batch mode and thus always need to persist their results either in a table or in a file. U-SQL’s [`OUTPUT`](output-statement-u-sql.md) statement writes the specified rowset to the provided file path URI. The file path URI is specified either as a relative or absolute Azure Data Lake Storage file path URI, a Windows Azure Blob Storage file path URI or a simplified path pattern expression.   
  
* Since file paths are URIs, characters such as spaces need to be _URI-encoded_. For example the file name `a has 3 spaces` has to be written as `a%20has%203%20spaces`.  
  
* A file path URI has to be provided as a [static string expression](expressions-u-sql.md) (an expression that can be constant folded) in the `TO` clause of an [`OUTPUT`](output-statement-u-sql.md) expression.  
  
* A file path can also be specified as a local file path.  
  
A local Azure Data Lake Storage file path (without the URI header) refers to a path in the Azure Data Lake Analytics account’s associated default Data Lake account.  
  
The following grammar rules shows the syntax for each of the supported paths:  
## Syntax  
<pre>
Output_File_Path := 
    <a href="input-files-u-sql.md#defaultaccountpath">Default_Account_Path_URI</a> 
|   <a href="input-files-u-sql.md#adlpath">ADL_Path_URI</a> 
|   <a href="input-files-u-sql.md#wasbpath">WASB_Path_URI</a> 
|   Simple_File_Set_Path.
</pre>
  
The grammar rules [`Default_Account_Path_URI`](input-files-u-sql.md#defaultaccountpath), [`ADL_Path_URI`](input-files-u-sql.md#adlpath) and [`WASB_Path_URI`](input-files-u-sql.md#wasbpath) are specified in [Input Files (U-SQL)](input-files-u-sql.md).   
  
## Output File Sets  
Unlike the input file paths, the output file path only supports a simplified file set path that can contain a single unnamed wildcard. The grammar rule `Simple_File_Set_Path` is defined as:

  ### Syntax   
  <pre>
  Simple_File_Set_Path :=
      [ADL_Header | WebHDFS_Header | WASB_Header]+Simple_FileSet_Pattern.<br />
  Simple_FileSet_Pattern := 
      '/'+{directory_name +'/'}+ file_name | Simple_File_Name_Pattern.<br />
  Simple_File_Name_Pattern := 
      [{character}] Wildcard_Pattern [{character}].<br />
  Wildcard_Pattern := 
      '{*}'.
  </pre>

  If a `Simple_File_Set_Path` is specified in an [OUTPUT](output-statement-u-sql.md)    statement, the statement will create as many files as there were processing nodes that were processing the output rowset. Each file name will contain the node’s id in place of the `Wildcard_Pattern`.  
 
## Examples    
- The example(s) can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The example(s) below are based on the dataset(s) defined below.  Ensure your execution includes the rowset variable(s).  

**Dataset**  
```SQL
    SELECT * FROM 
        ( VALUES
        (1, "Noah",   100, (int?)10000, new DateTime(2012,05,31)),
        (2, "Sophia", 100, (int?)15000, new DateTime(2012,03,19)),
        (3, "Liam",   100, (int?)30000, new DateTime(2014,09,14)),
        (4, "Amy",    100, (int?)35000, new DateTime(1999,02,27)),
        (5, "Justin", 600, (int?)15000, new DateTime(2015,01,12)),
        (6, "Emma",   200, (int?)8000,  new DateTime(2014,03,08)),
        (7, "Jacob",  200, (int?)8000,  new DateTime(2014,09,02)),
        (8, "Olivia", 200, (int?)8000,  new DateTime(2013,12,11)),
        (9, "Mason",  300, (int?)50000, new DateTime(2016,01,01)),
        (10, "Ava",   400, (int?)15000, new DateTime(2014,09,14))
        ) AS T(EmpID, EmpName, DeptID, Salary, StartDate);
```

**Default_Account_Path_URI**   
```sql
@result = 
    SELECT *
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/Concepts/FileSets/Output/defaultAccountPath.csv" 
USING Outputters.Csv();
```

**ADL_Path_URI**   
```sql
@result =
    SELECT *
    FROM @employees;

OUTPUT @result
TO "adl://<adl_accountname>.azuredatalakestore.net/ReferenceGuide/Concepts/FileSets/Output/adlPath.csv"
USING Outputters.Csv();
```

**WASB_Path_URI**  
```sql
@result =
    SELECT *
    FROM @employees;

OUTPUT @result
TO  "wasb://<wasb_container>@<wasb_accountname>/ReferenceGuide/Concepts/FileSets/Output/wasbPath.csv"
USING Outputters.Csv();
```
 
 **Simple_File_Set_Path**  
 ```sql
@result =
    SELECT *
    FROM @employees;

OUTPUT @result
TO "/ReferenceGuide/Concepts/FileSets/Output/sfsp{*}.csv"
USING Outputters.Csv();
 ```

 
## See Also
- [U-SQL Built-in Outputters](u-sql-built-in-outputters.md)
- [OUTPUT Statement (U-SQL)](output-statement-u-sql.md)
- [Files and File Sets as Inputs and Outputs (U-SQL)](files-and-file-sets-as-inputs-and-outputs-u-sql.md)
- [Input Files (U-SQL)](input-files-u-sql.md)  
