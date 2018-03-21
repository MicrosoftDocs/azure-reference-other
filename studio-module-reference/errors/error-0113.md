---
title: "Error 0113 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0113-d185d1509344
caps.latest.revision: 7
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0113  
 Thrown when a module definition file contains errors.  
  
 This error in Azure Machine Learning is produced when the custom module XML definition file can be parsed but contains errors, such as definition of elements not supported by custom modules.  
  
## Resolution  
 Make sure the custom module definition file defines elements and properties that are supported by custom modules.  
  
|Exception Messages|  
|------------------------|  
|Module definition file contains errors.|  
|Module definition file '{0}' contains errors.|  
|Module definition file '{0}' contains errors. {1}|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)