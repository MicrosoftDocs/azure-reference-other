---
title: "DROP CREDENTIAL (U-SQL) | Microsoft Docs"
ms.custom: ""
ms.date: "2017-08-22"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 06a4742e-d625-450d-9977-ebd317c1fd4c
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# DROP CREDENTIAL (U-SQL)
> [!WARNING] 
> The CREATE/ALTER/DROP CREDENTIAL statements are deprecated and have been removed. Use the credential management commandlets in the latest Azure Powershell.   
> See [Set-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/resourcemanager/azurerm.datalakeanalytics/v2.3.0/set-azurermdatalakeanalyticscatalogcredential) for information on creating and managing an Azure Data Lake Analytics catalog credential.

### See Also
* [New-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/module/azurerm.datalakeanalytics/new-azurermdatalakeanalyticscatalogcredential?view=azurermps-4.3.1)
* [Set-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/module/azurerm.datalakeanalytics/set-azurermdatalakeanalyticscatalogcredential?view=azurermps-4.3.1)
* [Remove-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/module/azurerm.datalakeanalytics/remove-azurermdatalakeanalyticscatalogcredential?view=azurermps-4.3.1)


\<!--
> [!WARNING] 
> CREATE/ALTER/DROP CREDENTIAL statements are deprecated and will be removed in the next deployment. Use credential management commandlets in the latest Azure Powershell.
> See [Remove-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/en-us/powershell/resourcemanager/azurerm.datalakeanalytics/v2.3.0/remove-azurermdatalakeanalyticscatalogcredential) for information on deleting an Azure Data Lake Analytics catalog credential.

A credential can be dropped with the `DROP CREDENTIAL` statement. If the credential is being referenced by a data source, the command will fail.  
  
> [!WARNING]
> **This operation cannot be undone!**
  
<table><th>Syntax</th><tr><td><pre>
Drop_Credential_Statement :=                                                                             
    'DROP' 'CREDENTIAL' [<a href="#IE">'IF' 'EXISTS'</a>] <a href="#ci">Credential_Identifier</a>.
<br />
<a href="#ci">Credential_Identifier</a> := 
    <a href="u-sql-identifiers.md">Quoted_or_Unquoted_Identifier</a>.
</pre></td></tr></table>

### Semantics of Syntax Elements    
-   <a name="ci"></a>**`Credential_Identifier`**   
Specifies the credential in the current static database context to be dropped. If a credential of the given name does not exist, or the user has no permissions to drop the credential, an error is raised.  
  
-   <a name="IE"></a>**`IF EXISTS`**    
If the optional `IF EXISTS` is specified, then the statement drops the credential if it already exists, or succeeds without changes if the credential does not exist or the user has no permission to at least enumerate all existing credentials.  
  
### Example    
The following script deletes the CREDENTIAL `ExampleSecret` if it exists from the `SampleDB` database. If there is a data source still referring to the credential object, an error will be raised:  
  
```
USE DATABASE SampleDB;  
DROP CREDENTIAL IF EXISTS ExampleSecret;  
```
  
### See Also
* [U-SQL Credential Objects](u-sql-credential-objects.md)  
* [CREATE CREDENTIAL (U-SQL)](create-credential-u-sql.md)  
* [ALTER CREDENTIAL (U-SQL)](alter-credential-u-sql.md)  
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md) 
-->  

