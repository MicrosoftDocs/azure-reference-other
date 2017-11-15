---
title: "Output to Files (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 071f1a22-451f-4dc0-96da-8a979d4fe85c
caps.latest.revision: 11
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Output to Files (U-SQL)
Currently U-SQL scripts are executed in batch mode and thus always need to persist their results either in a table or in a file. U-SQL’s [`OUTPUT`](output-statement-u-sql.md) statement writes the specified rowset to the provided file path URI. The file path URI is specified either as a relative or absolute Azure Data Lake Storage file path URI, a Windows Azure Blob Storage file path URI or a simplified path pattern expression.   
  
* Since file paths are URIs, characters such as spaces need to be _URI-encoded_. For example the file name `a has 3 spaces` has to be written as `a%20has%203%20spaces`.  
  
* A file path URI has to be provided as a [static string expression](expressions-u-sql.md) (an expression that can be constant folded) in the `TO` clause of an [`OUTPUT`](output-statement-u-sql.md) expression.  
  
* A file path can also be specified as a local file path.  
  
A local Azure Data Lake Storage file path (without the URI header) refers to a path in the Azure Data Lake Analytics account’s associated default Data Lake account.  
  
The following grammar rules shows the syntax for each of the supported paths:  
<table><th align="left">Syntax</th><tr><td><pre>
Output_File_Path :=                                                                                      
     <a href="input-files-u-sql.md#defaultaccountpath">Default_Account_Path_URI</a> 
|    <a href="input-files-u-sql.md#adlpath">ADL_Path_URI</a> 
|    <a href="input-files-u-sql.md#wasbpath">WASB_Path_URI</a> 
|    Simple_File_Set_Path.
</pre></td></table>
  
The grammar rules `Default_Account_Path_URI`, `ADL_Path_URI` and `WASB_Path_URI` are specified in [Input Files (U-SQL)](input-files-u-sql.md).   
  
### Output File Sets  
Unlike the input file paths, the output file path only supports a simplified file set path that can contain a single unnamed wildcard. The grammar rule `Simple_File_Set_Path` is defined as:  
<table><th align="left">Syntax</th><tr><td><pre>
Simple_File_Set_Path :=                                                                                  
     [ADL_Header | WebHDFS_Header | WASB_Header]+Simple_FileSet_Pattern.<br />
Simple_FileSet_Pattern := 
     '/'+{directory_name +'/'}+ file_name | Simple_File_Name_Pattern.<br />
Simple_File_Name_Pattern := 
     [{character}] Wildcard_Pattern [{character}].<br />
Wildcard_Pattern := 
     '{*}'.
</pre></td></table>

If a `Simple_File_Set_Path` is specified in an [OUTPUT](output-statement-u-sql.md)    statement, the statement will create as many files as there were processing nodes that were processing the output rowset. Each file name will contain the node’s id in place of the `Wildcard_Pattern`.  
 
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The examples below uses the sample data provided with your Data Lake Analytics account. See [Prepare source data](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal#prepare-source-data) for additional information.
- The sample data is used to create and populate the table defined below:
```
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE DATABASE TestReferenceDB; 

DROP TABLE IF EXISTS dbo.SearchLog;
CREATE TABLE dbo.SearchLog (
       INDEX sl_idx CLUSTERED (UserId ASC) 
       DISTRIBUTED BY HASH (UserId) INTO 2
) AS  
    EXTRACT UserId          int  
          , Start           DateTime  
          , Region          string  
          , Query           string  
          , Duration        int  
          , Urls            string  
          , ClickedUrls     string
    FROM "/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv();
```

**Default_Account_Path_URI**   
```
@result = 
    SELECT *
    FROM TestReferenceDB.dbo.SearchLog;

OUTPUT @result
TO "/Samples/Outputs/ReferenceGuide/OutA.csv" 
USING Outputters.Csv();
```

**ADL_Path_URI**   
```
@result =
    SELECT *
    FROM TestReferenceDB.dbo.SearchLog;

OUTPUT @result
TO "adl://<adl_accountname>.azuredatalakestore.net/Samples/Outputs/ReferenceGuide/OutB.csv"
USING Outputters.Csv();
```

**WASB_Path_URI**  
```
@result =
    SELECT *
    FROM TestReferenceDB.dbo.SearchLog;

OUTPUT @result
TO "wasb://<wasb_container>@<wasb_accountname>/ReferenceGuide/OutC.csv"
USING Outputters.Csv();
```
 
 **Simple_File_Set_Path**  
 ```
@result =
    SELECT *
    FROM TestReferenceDB.dbo.SearchLog;

OUTPUT @result
TO "/Samples/Outputs/ReferenceGuide/Out{*}.csv"
USING Outputters.Csv();
 ```

 
### See Also
- [U-SQL Built-in Outputters](u-sql-built-in-outputters.md)
- [OUTPUT Statement (U-SQL)](output-statement-u-sql.md)
- [Files and File Sets as Inputs and Outputs (U-SQL)](files-and-file-sets-as-inputs-and-outputs-u-sql.md)
- [Input Files (U-SQL)](input-files-u-sql.md)  
