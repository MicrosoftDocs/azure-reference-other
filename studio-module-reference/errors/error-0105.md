---
title: "Error 0105 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0105  
 This error is displayed when a module definition file contains an unsupported parameter type  
  
 This error in Azure Machine Learning is produced when the you create a custom module xml definition and the type of a parameter or argument in the definition does not match a supported type.  
  
**Resolution :**
 Make sure that the type property of any **Arg** element in the custom module xml definition file is a supported type.  
  
|Exception Messages|  
|------------------------|  
|Unsupported parameter type.|  
|Unsupported parameter type '{0}' specified.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
