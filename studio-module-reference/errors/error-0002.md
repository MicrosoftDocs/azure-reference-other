---
title: "Error 0002 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0002-d185d1509344
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0002  
 Exception occurs if one or more parameters could not be parsed or converted from specified type into required by target method type.  
  
 This error occurs in Azure Machine Learning when you specify a parameter as input and the value type is different from the type that is expected, and implicit conversion cannot be performed.  
  
## Resolution  
 Check the module requirements and determine which value type is required (string, integer, double, etc.)  
  
|Exception Messages|  
|------------------------|  
|Failed to parse parameter|  
|Failed to parse "{0}" parameter|  
|Failed to parse (convert) "{0}" parameter to "{1}"|  
|Failed to convert "{0}" parameter from "{1}" to "{2}"|  
|Failed to convert "{0}" parameter value "{1}" from "{2}" to "{3}"|  
|Failed to convert value "{0}" in column "{1}" from "{2}" to "{3}" with usage of the format "{4}" provided|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)