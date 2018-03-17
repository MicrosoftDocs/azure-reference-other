---
title: "U-SQL Database Schemas | Microsoft Docs"
ms.custom: ""
ms.date: "04/04/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: ddcdc4e7-75c3-4678-a662-20a3ab433e55
caps.latest.revision: 16
author: "MikeRys"
ms.author: "mrys"
manager: "Ryan.Waite"
---
# U-SQL Database Schemas
Similar to other database systems and ANSI SQL, U-SQL uses the concept of a schema to group related objects together in the context of a database.   
  
U-SQL provides a built-in schema within each database called dbo that is used as the default schema context. Additionally, U-SQL provides the ability to create and delete additional schemas with schema DDL statements.  
  
### Schema DDL Statements
<table><th align="left">Syntax</th><tr><td><pre>
Schema_DDL_Statement :=                                                                                  
     <a href="create-schema-u-sql.md">Create_Schema_Statement</a>
|    <a href="drop-schema-u-sql.md">Drop_Schema_Statement</a>.
</pre></td></tr></table>

A list of schema can be retrieved using the Windows PowerShell cmdlet [Get-AzureRmDataLakeAnalyticsCatalogItem](https://docs.microsoft.com/powershell/resourcemanager/azurerm.datalakeanalytics/v2.7.0/get-azurermdatalakeanalyticscatalogitem).  Example command for retrieving schema from the `TestReferenceDB` database.
```powershell
Login-AzureRmAccount;
$DataLakeAnalyticsAccount = "<adla_account>";

Get-AzureRmDataLakeAnalyticsCatalogItem -Account $DataLakeAnalyticsAccount -Path "TestReferenceDB" -ItemType "Schema";
(Get-AzureRmDataLakeAnalyticsCatalogItem -Account $DataLakeAnalyticsAccount -Path "TestReferenceDB" -ItemType "Schema").Name;
```
  
### See Also    
* [CREATE SCHEMA (U-SQL)](create-schema-u-sql.md)
* [USE SCHEMA (U-SQL)](use-schema-u-sql.md) 
* [DROP SCHEMA (U-SQL)](drop-schema-u-sql.md)
