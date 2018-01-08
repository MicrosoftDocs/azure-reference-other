---
title: "Securing Meta Data Objects | Microsoft Docs"
ms.custom: ""
ms.date: "03/10/2017"
ms.reviewer: ""
ms.service: "data-lake-analytics"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: d2c005a9-bc52-48ff-aea5-695775f4f6cb
caps.latest.revision: 8
author: "edmacauley"
ms.author: "edmaca"
manager: "jhubbard"
---
# Securing Meta Data Objects
The U-SQL’s metadata is secured in the context of the Azure subscription’s Active Directory and the Azure Data Lake’s default Azure Data Lake Storage account. The Active Directory provides the Security Principals such as users and security groups.  
  
The U-SQL authorization model is using the authorization of the physical parts of the objects in the Azure Data Lake Storage to provide authorization on the metadata object.  
  
In the Public Preview, this means that the authorization on the default Azure Data Lake Storage account will set the authorization on the U-SQL’s metadata catalog. Thus, a user or security group that has write access to the Azure Data Lake’s default storage account will have the right to create or delete databases or tables through U-SQL and a user or security group that has read access but no write access can only query the data. In future updates, Azure Data Lake Storage will provide finer granularity permissions at the folder and file level and U-SQL will then provide finer granularity permissions, such as at the database level or table level.  
  
Currently there is no Data Definition Language in U-SQL to manage permissions. Instead, the permissions are set at the default storage account and will be inherited by the catalog.  

## Catalogs can be Shared Among ADLA Accounts   
You can use 4 part-names to access U-SQL catalog objects from a different Azure Data Lake Analytics account.  The following conditions and restrictions apply:

1. As in the primary catalog, database and catalog level access control needs to permit referring to the objects.
2. The ADLS and ADLA accounts need to be in the same Azure region.
3. You cannot create meta data objects in the other ADLA account's meta data object. Thus you cannot invoke any DDL statement with a 4-part name, nor invoking a U-SQL procedure.
4. You cannot insert into a table of a different account.
