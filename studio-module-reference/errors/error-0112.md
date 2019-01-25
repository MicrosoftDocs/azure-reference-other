---
title: "Error 0112 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.subservice: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0112-d185d1509344
caps.latest.revision: 7
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0112  
 Thrown when a module definition file cannot be parsed  
  
 This error in Azure Machine Learning is produced when there is an error in the xml format that prevents the custom module XML definition from being parsed as a valid XML file.  
  
## Resolution  
 Ensure that each element is opened and closed correctly. Make sure that there are no errors in the XML formatting.  
  
|Exception Messages|  
|------------------------|  
|Unable to parse module definition file.|  
|Unable to parse module definition file '{0}'.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
