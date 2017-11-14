---
title: "U-SQL Procedures | Microsoft Docs"
ms.custom: ""
ms.date: "2017-08-21"
ms.prod: "azure"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 70d3cbcb-ea15-42f0-910c-de3929fa863c
caps.latest.revision: 16
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Procedures
U-SQL provides the ability to name scripts as procedures and parameterize them. Unlike procedures in other query languages, such as T-SQL or PL/SQL, U-SQL’s procedures do **not** provide any imperative code-flow constructs such as a `for` or `while` loops. Its main differences to U-SQL functions are:    
1.  U-SQL Procedures do not provide return values    
2.  U-SQL Procedures can create and output to files and insert into tables.  
3.  U-SQL Procedures can contain data-definition (DDL) statements to create, alter or drop U-SQL metadata objects (except procedures and functions).
  
  
### Procedure DDL Statements    
U-SQL provides the ability to create or drop procedures:  
  
<table><th>Syntax</th><tr><td><pre>
Procedure_DDL_Statement :=                                                                               
    <a href="create-procedure-u-sql.md">Create_Proc_Statement</a>  
|   <a href="drop-procedure-u-sql.md">Drop_Proc_Statement</a>.  
</pre></td></tr></table>

Procedures can be used inside other procedures and U-SQL scripts.  

A list of procedures can be retrieved using the Windows PowerShell cmdlet [Get-AzureRmDataLakeAnalyticsCatalogItem](https://docs.microsoft.com/powershell/resourcemanager/azurerm.datalakeanalytics/v2.7.0/get-azurermdatalakeanalyticscatalogitem).  Example command for retrieving procedures from the `TestReferenceDB` database.
```powershell
Login-AzureRmAccount;
$DataLakeAnalyticsAccount = "<adla_account>";

Get-AzureRmDataLakeAnalyticsCatalogItem -Account $DataLakeAnalyticsAccount -Path "TestReferenceDB.dbo" -ItemType "Procedure";
(Get-AzureRmDataLakeAnalyticsCatalogItem -Account $DataLakeAnalyticsAccount -Path "TestReferenceDB.dbo" -ItemType "Procedure").Name;
```
  
### See Also
* [CREATE PROCEDURE (U-SQL)](create-procedure-u-sql.md)  
* [DROP PROCEDURE (U-SQL)](drop-procedure-u-sql.md)  
* [Calling a Procedure (U-SQL)](calling-a-procedure-u-sql.md)  
 
