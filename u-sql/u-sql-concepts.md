---
title: "U-SQL Concepts | Microsoft Docs"
ms.custom: ""
ms.date: "2017-04-07"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2854662d-8d7b-4589-bbc5-a50b505a943a
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Concepts
U-SQL combines some familiar concepts from a variety of languages: It is a *declarative* language like SQL, it follows a *dataflow-like composition of statements and expressions* like Pig and Cascading*,* and provides simple ways to *extend the language* with [user-defined operators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-objects--udo), [user-defined aggregators](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-aggregates--udagg) and [user-defined functions](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide#user-defined-functions---udf) using C#, and provides a SQL database-like metadata object model to manage, discover and secure structured data and user-code.  

## How does a U-SQL Script process your Data
Currently, Azure Data Lake Analytics provides U-SQL for batch processing.  Therefore U-SQL is written and executed in form of a batch script. It follows the following general processing pattern:    
1.  Retrieve data from stored locations in rowset format    
    1.  Stored locations can be files that will be schematized on read with [EXTRACT](extract-expression-u-sql.md) expressions    
    2.  Stored locations can be U-SQL tables that are stored in a schematized format    
    3.  Or can be tables provided by other data sources such as an Azure SQL database.     
    

2.  Transform the rowset(s)    
    1.  Several transformations over the rowsets can be composed in a data flow format    
    
    
3.  Store the transformed rowset data    
    1.  Store it in a file with an [OUTPUT](output-statement-u-sql.md) statement, or    
    2.  Store it in a U-SQL table with an [INSERT](insert-u-sql.md) statement    

In addition, U-SQL also supports data definition statements such as [CREATE TABLE](create-table-u-sql-creating-a-table-with-schema.md) to create metadata artifacts either in separate scripts or sometimes even in combination with the transformation scripts.  
  
U-SQL Scripts can be submitted in a variety of ways. In particular you can submit them directly from within the [Azure Data Lake Tools for Visual Studio](https://azure.microsoft.com/en-us/documentation/articles/data-lake-analytics-data-lake-tools-get-started/), from the [Azure Portal](https://azure.microsoft.com/en-us/documentation/articles/data-lake-analytics-get-started-portal) or programmatically via the [Azure Data Lake SDK](https://azure.microsoft.com/en-us/documentation/articles/data-lake-analytics-get-started-net-sdk/) job submission API or the [Azure Powershell](https://azure.microsoft.com/en-us/documentation/articles/data-lake-analytics-get-started-powershell) extension's job submission command.  
  
Please explore the following concepts introduced in this section:  
* [U-SQL Script Structure](u-sql-scripts.md)  
* [Expressions](expressions-u-sql.md)
* [Files and File Sets as Inputs and Outputs](files-and-file-sets-as-inputs-and-outputs-u-sql.md) 
* [Identifiers](identifiers-u-sql.md)  
* [Metadata system and objects](data-definition-language-ddl-statements-u-sql.md) 
* [Rowset: The Processing Data Structure](rowset-the-processing-data-structure-u-sql.md)  
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)



