---
title: "U-SQL Credential Objects | Microsoft Docs"
ms.custom: ""
ms.date: "2017-08-22"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5a3f808c-8638-4710-98d3-3160a8e4d5ed
caps.latest.revision: 17
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# U-SQL Credential Objects
> [!WARNING] 
> The CREATE/ALTER/DROP CREDENTIAL statements are deprecated and have been removed. Use the credential management commandlets in the latest Azure Powershell.   
> See [Set-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/resourcemanager/azurerm.datalakeanalytics/v2.3.0/set-azurermdatalakeanalyticscatalogcredential) for information on creating and managing an Azure Data Lake Analytics catalog credential.


U-SQL’s data sources may require the specification of login credentials (username/password) if the data source is not using integrated authentication via Azure Active Directory. In order to provide secure management of these credentials, one has to use a combination of [PowerShell script commands](https://azure.microsoft.com/en-us/documentation/articles/data-lake-analytics-get-started-powershell/) to encode and encrypt the password into the key store and then register the key store reference in the meta data service so it can be used when creating a data source object.  
 
 <!--
### Credential DDL Statements    
The following statements are available to manage the credentials:  
  
<table><th>Syntax</th><tr><td><pre>
Credential_DDL_Statement :=                                                                              
    <a href="create-credential-u-sql.md">Create_Credential_Statement</a> 
|   <a href="alter-credential-u-sql.md">Alter_Credential_Statement</a>  
|   <a href="drop-credential-u-sql.md">Drop_Credential_Statement</a>.  
</pre></td></tr></table>
 -->
  
### See Also 
* [New-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/resourcemanager/azurerm.datalakeanalytics/v2.3.0/new-azurermdatalakeanalyticscatalogcredential)
* [Set-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/resourcemanager/azurerm.datalakeanalytics/v2.3.0/set-azurermdatalakeanalyticscatalogcredential)
* [Remove-AzureRmDataLakeAnalyticsCatalogCredential](https://docs.microsoft.com/powershell/resourcemanager/azurerm.datalakeanalytics/v2.3.0/remove-azurermdatalakeanalyticscatalogcredential)  
* [Data Definition Language (DDL) Statements (U-SQL)](data-definition-language-ddl-statements-u-sql.md)   

 


 