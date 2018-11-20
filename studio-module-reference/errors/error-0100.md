---
title: "Error 0100 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0100-d185d1509344
caps.latest.revision: 7
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0100  
 Exception occurs when an unsupported language is specified for a custom module.  
  
 This error in Azure Machine Learning occurs when building a custom module and the name property of the **Language** element in a custom module xml definition file has an invalid value. Currently, the only valid value for this property is `R`. For example:  
  
 `<Language name="R" sourceFile="CustomAddRows.R" entryPoint="CustomAddRows" />`  
  
## Resolution  
 Verify that the name property of the **Language** element in the custom module xml definition file is set to `R`. Save the file, update the custom module zip package, and try to add the custom module again.  
  
|Exception Messages|  
|------------------------|  
|Unsupported custom module language specified|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
