---
title: "Error 0048 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0048-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0048  
 Exception occurs in the case when it is not possible to open a file.  
  
 This error in Azure Machine Learning occurs when it is not possible to open a file for read or write. You might receive this error for these reasons:  
  
-   The container or the file (blob) does not exist  
  
-   The access level of the file or container does not allow you to access the file  
  
-   The file is too large to read or the wrong format  
  
## Resolution  
 Revisit the module and the file you are trying to read.  
  
 Verify that the names of the container and file are correct.  
  
 Use the Azure management portal or an Azure storage tool to verify that you have permission to access the file.  
  
 If you are trying to read an image file, make sure that it meets the requirements for image files in terms of size, number of pixels, and so forth. For more information, see [Import Images](../import-images.md).  
  
|Exception Messages|  
|------------------------|  
|Unable to open a file.|  
|Error while opening the file: {0}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)