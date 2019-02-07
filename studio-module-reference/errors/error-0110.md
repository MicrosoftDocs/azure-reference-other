---
title: "Error 0110 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0110  
 Thrown when a module definition file defines a column picker that references a non existent input port ID  
  
 This error in Azure Machine Learning is produced when the *portId* property within the Properties element of an Arg of type ColumnPicker does not match the Id value of an input port.  
  
## Resolution  
 Make sure the portId property matches the id value of an input port defined in the custom module xml definition.  
  
|Exception Messages|  
|------------------------|  
|Column picker references a non existent input port ID.|  
|Column picker references a non existent input port ID '{0}'.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
