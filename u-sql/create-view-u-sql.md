---
title: "CREATE VIEW (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-03-10"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1b81aed5-c904-45be-ae5f-3725da8b0df1
caps.latest.revision: 7
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# CREATE VIEW (U-SQL)
The `CREATE VIEW` statement creates the view with the specified identifier based on the provided query expression. The view’s schema is inferred from the query’s result type.  
  
<table><th>Syntax</th><tr><td><pre>
Create_View_Statement :=                                                                                 
      'CREATE' 'VIEW' [<a href="#INE">'IF' 'NOT' 'EXISTS'</a>] <a href="#Ident">Identifier</a> 'AS' <a href="#qry_exp">Query_Expression</a>.  
</pre></td></table>
 
### Semantics of Syntax Elements    
-   <a name="Ident"></a>**`Identifier`**  
    Specifies the name of the view to be defined. If the `Identifier` is a three-part identifier, the view will be created in the specified database and schema. If it is a two-part identifier, then the view will be created in the specified schema of the current database context. If the identifier is a simple identifier, then the view will be created in the current database and schema context.  
  
    If an object of the given name already exists in the specified database and schema context or the user has no permissions to create a view, an error is raised.  
  
-   <a name="INE"></a>**`IF NOT EXISTS`**   
    If the optional `IF NOT EXISTS` is specified, then the statement creates the view if it does not already exist, or succeeds without changes if the view already exists and the user has permission to at least enumerate all existing views.  
  
-   <a name="qry_exp"></a>**`Query_Expression`**  
    The query expression defines the view’s schema and defines the query that will be executed every time the view gets referenced in a query.  
  
    The query expression is not allowed to refer to variables or user-defined objects like [user-defined functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf), [user-defined operators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo) or [user-defined types](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#using-user-defined-types---udt). Currently, the creation of the view will succeed, but subsequent invocations of the view will raise errors if they refer to variables or user-defined objects. Please use [table-valued functions](../USQL/u-sql-table-valued-functions.md) instead, if you need to use user-defined functions, operators or types.
      
### Examples    
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The examples below use the sample data provided with your Data Lake Analytics account. See [Prepare source data](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal#prepare-source-data) for additional information.

**View based on a table**     
The following example creates a view called `SampleView` based on the table `SampleTable` in `SampleDB`.  
```
CREATE VIEW SampleDB.dbo.SampleView  
    AS  
SELECT id,  
       name,  
       date  
  FROM SampleDB.dbo.SampleTable;  
```

**View based on an extraction**   
Subsequent queries against `SearchLog.tsv` can now be performed against the view without the need to constantly execute `EXTRACT`.
```
CREATE DATABASE IF NOT EXISTS TestReferenceDB;
USE DATABASE TestReferenceDB; 

DROP VIEW IF EXISTS SearchlogView;
CREATE VIEW SearchlogView AS  
    EXTRACT UserId          int,
            Start           DateTime,
            Region          string,
            Query           string,
            Duration        int?,
            Urls            string,
            ClickedUrls     string
    FROM "/Samples/Data/SearchLog.tsv"
    USING Extractors.Tsv();
```

### See Also    
- [U-SQL Views](../USQL/u-sql-views.md) 
- [DROP VIEW (U-SQL)](../USQL/drop-view-u-sql.md)
- [U-SQL Functions](../USQL/u-sql-functions.md)  
