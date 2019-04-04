---
title: "Error 0046 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0046  
 Exception occurs when it is not possible to create directory on specified path.  
  
 This error in Azure Machine Learning occurs when it is not possible to create a directory on the specified path. You will receive this error if any part of the path to the output directory for a Hive Query is incorrect or inaccessible.  
  
**Resolution :**
 Revisit the module and verify that the directory path is correctly formatted and that it is accessible with the current credentials.  
  
|Exception Messages|  
|------------------------|  
|Please specify a valid output directory.|  
|Directory: {0} cannot be created. Please specify valid path.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
