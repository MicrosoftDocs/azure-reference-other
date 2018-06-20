---
title: "U-SQL Language Reference | Microsoft Docs"
ms.custom: ""
ms.date: "10/11/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "U-SQL"
ms.assetid: e99e2a4c-2d78-4a7e-92d0-81ca0b57c25e
caps.latest.revision: 32
author: "MikeRys"
ms.author: "mrys"
manager: "ryanw"
---

# U-SQL Language Reference

## Introduction    
This is the reference documentation for the U-SQL language.  
  
## What is U-SQL?    
U-SQL is the new big data query language of the Azure Data Lake Analytics service.  
  
It evolved out of Microsoft's internal Big Data language called [SCOPE](http://www.vldb.org/pvldb/1/1454166.pdf) and combines a familiar SQL-like declarative language with the extensibility and programmability provided by C# types and the C# expression language and big data processing concepts such as “schema on reads”, custom processors and reducers. It also provides the ability to query and combine data from a variety of data sources, including Azure Data Lake Storage, Azure Blob Storage, and Azure SQL DB, Azure SQL Data Warehouse, and SQL Server instances running in Azure VMs.  
  
It is however not ANSI SQL. For starters, its keywords such as SELECT have to be in UPPERCASE. And its expression language inside SELECT clauses, WHERE predicates etc is C#. This for example means, that the comparison operations inside a predicate follow C# syntax (e.g., a == "foo"), and that the language uses C# null semantics which is 2-valued and not 3-valued as in ANSI SQL. To help SQL users to get familiar with U-SQL, a section is providing the mapping of some common SQL expressions and how to express them in U-SQL.  

## Overview of the Language Reference    
The language reference is organized as follows:    
1. This introduction provides a quick introduction and overview of the reference documentation.  
2. Introduction of the U-SQL concepts   
    a. [U-SQL Processing Model](u-sql-concepts.md)  
    b. [U-SQL Script Structure](u-sql-scripts.md)  
    c. [Files and File Sets as Inputs and Outputs](files-and-file-sets-as-inputs-and-outputs-u-sql.md)  
    d. [Rowset: The Processing Data Structure](rowset-the-processing-data-structure-u-sql.md)  
    e. [U-SQL Identifiers](identifiers-u-sql.md)  
    f. [U-SQL Expressions](expressions-u-sql.md)  
    g. [Metadata system and objects](data-definition-language-ddl-statements-u-sql.md)  
    h. [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
    
3.  Syntax and Semantics of the U-SQL Language  
    a. [Data Types and Literals](data-types-and-literals-u-sql.md)   
    b.  [Data Definition Language (DDL) Statements](data-definition-language-ddl-statements-u-sql.md)  
    c.  [U-SQL Query Language](query-statements-and-expressions-u-sql.md)  
    d.  [Data Modification Language (DML) Statements](data-modification-language-dml-statements-u-sql.md)   
    e.  [Outputting to files with U-SQL](output-statement-u-sql.md)  
    f.  [Built-in Functions](built-in-functions-u-sql.md)
4. [How to express common SQL expressions in U-SQL](common-sql-expressions-in-u-sql.md)  

If you are interested in seeing how you use the above concepts to solve certain scenarios please refer to the Language User Guide, [tutorials](https://azure.microsoft.com/en-us/documentation/articles/data-lake-analytics-u-sql-get-started/) as well as the [U-SQL Programmability Guide](https://docs.microsoft.com/en-us/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide).  
  
## See Also  
* In order to see how the above concepts can be applied to solve certain scenarios, please refer to the following:   
    * [U-SQL Tutorials](https://azure.microsoft.com/en-us/documentation/articles/data-lake-analytics-u-sql-get-started/)   
    * [U-SQL Programmability Guide](https://docs.microsoft.com/en-us/azure/data-lake-analytics/data-lake-analytics-u-sql-programmability-guide) 
* For additional information please refer to:  
    * [Release Notes](https://github.com/Azure/AzureDataLake/tree/master/docs/Release_Notes) 
    * U-SQL C# Developer’s Guide (under development)  
    * U-SQL Best Practices and Optimizations (under development)  
    * [U-SQL Git Repo](https://github.com/Azure/USQL)  
    * [Azure Data Lake](http://azure.github.io/AzureDataLake/)
    * [Get Started with Azure Data Lake Analytics using Azure portal](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-get-started-portal)
    * [Introducing Azure Data Lake by Microsoft Virtual Academy](https://mva.microsoft.com/training-courses/introducing-azure-data-lake-17795?l=fxAzPGt9D_111787171)
* Tools
    * [Microsoft Azure Data Lake and Stream Analytics Tools for Visual Studio](https://www.microsoft.com/en-us/download/details.aspx?id=49504)
