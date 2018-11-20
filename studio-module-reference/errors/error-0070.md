---
title: "Error 0070 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0070-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0070  
 Exception occurs when attempting to access non-existent Azure table.  
  
 This error in Azure Machine Learning occurs when you attempt to access a non-existent Azure table. You will receive this error if you specify a table in Azure storage which does not exist when reading from or writing to Azure Table Storage. This can happen if you mistype the name of the desired table, or you have a mismatch between the target name and the storage type. For example, you intended to read from a table but entered the name of a blob instead.  
  
## Resolution  
 Revisit the module to verify that the name of the table is correct.  
  
|Exception Messages|  
|------------------------|  
|Azure table does not exist.|  
|Azure table "{0}" does not exist.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)