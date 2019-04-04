---
title: "Error 0107 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0107  
 Thrown when a module definition file defines an unsuppported output type  
  
 This error in Azure Machine Learning is produced when the type of an output port in a custom module xml definition does not match a supported type.  
  
**Resolution :**
 Make sure that the type property of an Output element in the custom module xml definition file is a supported type.  
  
|Exception Messages|  
|------------------------|  
|Unsupported output type.|  
|Unsupported output type '{0}' specified.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
