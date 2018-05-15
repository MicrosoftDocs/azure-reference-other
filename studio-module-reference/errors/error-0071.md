---
title: "Error 0071 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 08/25/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0071-d185d1509344
caps.latest.revision: 8
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0071  
 Exception occurs if provided credentials are incorrect.  
  
 This error in Azure Machine Learning occurs if the provided credentials are incorrect.  
  
 You might also receive this error if the module cannot connect to an HDInsight cluster.  
  
## Resolution  
 Review the inputs to the module and verify the account name and password.  
  
 Check for the following issues that can cause an error:  
  
-   The schema of the dataset does not match the schema of the destination datatable.  
  
-   Column names are missing or misstyped.  
  
-   You are writing to a table that has column names with illegal characters. Ordinarily you can enclose such column names in square brackets , but if that does not work, edit column names to use only letters and underscores (_)  
  
-   Strings that you are trying to write contain single quotation marks  
  
 If you are trying to connect to an HDInsight cluster, verify that the target cluster is accessible with the supplied credentials.  
  
|Exception Messages|  
|------------------------|  
|Incorrect credentials are passed.|  
|Incorrect username "{0}" or password is passed|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)