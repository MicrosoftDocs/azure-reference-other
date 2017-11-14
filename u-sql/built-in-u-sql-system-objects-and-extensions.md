---
title: "Built-in U-SQL System Objects and Extensions | Microsoft Docs"
ms.custom: ""
ms.date: "2017-09-27"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 527c7c01-3755-4d04-b85c-5844a85c2583
caps.latest.revision: 4
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Built-in U-SQL System Objects and Extensions
U-SQL offers a set of built-in system objects and allows customers to install some extension libraries that provide additional capabilities to U-SQL.

## Built-in U-SQL System Objects

U-SQL provides a set of built-in catalog views that describe the content of the U-SQL Catalog for a specific Account and database. The catalog views are modelled after the SQL Server catalog views, but contain U-SQL specific information and live in the system-owned `usql` schema. 

See [Catalog Views (U-SQL)](catalog-views-u-sql.md) for a list of catalog views.

## U-SQL Extensions

The Azure Data Lake Analytics service offers the ability to install a set of extension libraries that enables customers to perform additional processing beyond the core U-SQL language.

The extensions are installed from the [Azure Data Lake Analytics Portal](http://portal.azure.com), and include the following capabilities:

-	[Scaling out Python scripts with U-SQL](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-python-extensions)
-	[Scaling out R scripts with U-SQL](https://docs.microsoft.com/azure/data-lake-analytics/data-lake-analytics-u-sql-r-extensions) 
-	[Cognitive Capabilities in U-SQL](cognitive-capabilities-in-u-sql.md) 



### See Also
* [Catalog Views (U-SQL)](catalog-views-u-sql.md)
* [usql.objects (U-SQL)](usql-objects-u-sql.md)
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)
* [Registering Cognitive Extensions in U-SQL](cognitive-capabilities-in-u-sql.md#registeringExtensions)
* [Extending U-SQL Expressions with User-Code](extending-u-sql-expressions-with-user-code.md)
* [Enabling U-SQL Advanced Analytics for Local Execution](https://blogs.msdn.microsoft.com/azuredatalake/2017/02/20/enabling-u-sql-advanced-analytics-for-local-execution/)

