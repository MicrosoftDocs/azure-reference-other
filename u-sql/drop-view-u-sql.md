---
title: "DROP VIEW (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b09c9ab9-afcb-4831-b1f0-3ad4894a28d9
caps.latest.revision: 5
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP VIEW (U-SQL)
A view can be dropped with the `DROP VIEW` statement. The statement drops the specified view but leaves the underlying data sources untouched.  
  
> [!WARNING]
> **This operation cannot be undone!**

<table><th align="left">Syntax</th><tr><td><pre>
Drop_View_Statement :=                                                                                   
    'DROP' 'VIEW' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#Ident">Identifier</a>.
</pre></td></table>

### Semantics of Syntax Elements    
-   <a name="Ident"></a>**`Identifier`**  
    Specifies the name of the view to be defined. If a view of the given name does not exist, or the user has no permissions to drop the view, an error is raised.  
  
-   <a name="IE"></a>**`IF EXISTS`**   
    If the optional `IF EXISTS` is specified, then the statement drops the view if it already exists, or succeeds without changes if the view does not exist or the user has no permission to at least enumerate all existing views.  
  
### Example    
- The example can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The script can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following statement deletes the view `SampleView` in the current database context and schema context if it exists and completes without changes if the view does not exist:  
  
```sql
DROP VIEW IF EXISTS TestReferenceDB.dbo.SampleView;  
```
  
### See Also  
- [U-SQL Views](u-sql-views.md)  
- [CREATE VIEW (U-SQL)](create-view-u-sql.md)
- [U-SQL Functions](u-sql-functions.md)
