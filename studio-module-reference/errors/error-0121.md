---
title: "Error 0121 | Microsoft Docs"
ms.custom: ""
ms.date: 11/09/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0121-d185d1509344
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0121
**Error 0121**  
  
 Thrown when SQL write fails because the table is unwriteable  
  
 This error in Azure Machine Learning is produced when you are using the [Export Data](../export-data.md) module to save results to a table in a SQL database, and the table cannot be written to. Typically, you will see this error if the [Export Data](../export-data.md) module successfully establishes a connection with the SQL Server instance, but is then unable to write the contents of the Azure ML dataset to the table.  
  
## Resolution  
 - Open the Properties pane of the [Export Data](../export-data.md) module and verify that the database and table names are entered correctly. 
 - Review the schema of the dataset you are exporting, and make sure that the data is compatile with the destination table.
 - Verify that the SQL login associated with the user name and password has permissions to write to the table. 
 - If the exception contains additional error information from SQL Server, use that information to make corrections.  
  
|Exception Messages|  
|------------------------|  
|Connected to server, unable to write to table.|  
|Unable to write to Sql table: {0}|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)