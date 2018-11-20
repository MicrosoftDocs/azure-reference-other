---
title: "Error 0026 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0026-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0026  
 Exception occurs if columns with the same name is not allowed.  
  
 This error in Azure Machine Learning occurs if multiple columns have the same name. One way you may receive this error is if the dataset does not have a header row and column names are automatically assigned: Col0, Col1, etc.  
  
## Resolution  
 If columns have same name, insert a [Edit Metadata](../edit-metadata.md) module between the input dataset and the module. Use the column selector in [Edit Metadata](../edit-metadata.md) to select columns to rename, typing the new names into the **New column names** textbox.  
  
|Exception Messages|  
|------------------------|  
|Equal column names are specified in arguments. Equal column names are not allowed by module.|  
|Equal column names in arguments "{0}" and "{1}" are not allowed. Please specify different names.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)