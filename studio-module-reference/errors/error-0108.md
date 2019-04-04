---
title: "Error 0108 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0108  
 Thrown when a module definition file defines more input or output ports than are supported  
  
 This error in Azure Machine Learning is produced when too many input or output ports are defined in a custom module xml definition.  
  
**Resolution :**
 Makes sure the maximum number of input and output ports defined in the custom module xml definition does not exceed the maximum number of supported ports.  
  
|Exception Messages|  
|------------------------|  
|Exceeded supported number of input or output ports.|  
|Exceeded number of supported '{0}' ports. Maximum allowed number of '{0}' ports is '{1}'.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
