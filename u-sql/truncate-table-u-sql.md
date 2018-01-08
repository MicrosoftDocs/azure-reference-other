---
title: "TRUNCATE TABLE (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 783f35bc-edaa-4b96-b388-e87590a1bb90
caps.latest.revision: 15
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# TRUNCATE TABLE (U-SQL)
U-SQL does not support fine-grained deletion of data with a DELETE statement. Data in a table can be deleted at the level of a vertical partition bucket, or by truncating the whole table with the `TRUNCATE TABLE` statement. Assuming the user executing the script has the right permissions, the `TRUNCATE TABLE` statement will keep the schema definition of the specified managed table intact and remove all the data contained within the table.   
  
> [!WARNING]
> **This operation cannot be undone!**

<table><th align="left">Syntax</th><tr><td><pre>
Truncate_Table_Statement :=                                                                              
     'TRUNCATE' 'TABLE' <a href="#ident">Identifier</a> [<a href="#ptl">Partition_Label_List</a>].
</pre></td></tr></table>
   
### Semantics of Syntax Elements  
- <a name="ident"></a>**`Identifier`**  
  Identifies the table to be truncated or truncated from. If the Identifier is a three-part identifier, the table from the specified database and schema will be truncated. If the Identifier is a two-part identifier, then the table of the given schema and of the given name of the current static database context will be truncated. If the identifier is a simple identifier, then the table of the given name in the current static database and schema context will be truncated.  

  If the specified table does not exist, is an external table, or the user has no permissions to delete the data from the table, an error is raised.   
  
- <a name="ptl"></a>**`Partition_Label_List`**  
  The optional partition label list specifies the list of partition buckets to be truncated by specifying the literal values for the partition columns. The values have to be provided as constants or as scalar static variables. For more details on the exact syntax see [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)
  
  
### Examples  
- The examples can be executed in Visual Studio with the [Azure Data Lake Tools plug-in](https://www.microsoft.com/download/details.aspx?id=49504).  
- The scripts can be executed [locally](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-data-lake-tools-get-started#run-u-sql-locally).  An Azure subscription and Azure Data Lake Analytics account is not needed when executed locally.

The following statement truncates the data in the table `SampleTable` in the database `TestReferenceDB`’s default schema `dbo`:  
```  
TRUNCATE TABLE TestReferenceDB..SampleTable;  
```  
  
The following statement truncates the data in the partition bucket with the value `5` in the vertically partitioned table `SampleTable` in the current database and schema context:  
```  
DECLARE @p int = 5;  
TRUNCATE TABLE SampleTable PARTITION (@p);  
```  
### See Also  
* [CREATE TABLE (U-SQL): Overview](create-table-u-sql-overview.md)  
* [ALTER TABLE (U-SQL): Adding and Removing Vertical Partition Buckets](alter-table-u-sql-adding-and-removing-vertical-partition-buckets.md)
* [DROP TABLE (U-SQL)](drop-table-u-sql.md)  
  
  
