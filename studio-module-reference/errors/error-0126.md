---
title: "Error 0126 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0126  
 Exception occurs if the user specifies a SQL domain that is not supported in Azure ML.  
  
 This error is produced when the user specifies a SQL domain that is not supported in Azure Machine Learning. You will receive this error if you are attempting to connect to a database server in a domain that is not whitelisted. Currently, the allowed SQL domains are: ".database.windows.net", ".cloudapp.net", or ".database.secure.windows.net". That is, the server must be an Azure SQL server or a server in a virtual machine on Azure.  
  
## Resolution  
 Revisit the module. Verify that the SQL database server belongs to one of the accepted domains:  
  
-   .database.windows.net  
  
-   .cloudapp.net  
  
-   .database.secure.windows.net  
  
|Exception Messages|  
|------------------------|  
|Unsupported SQL domain.|  
|The SQL domain {0} is not currently supported in Azure ML|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
