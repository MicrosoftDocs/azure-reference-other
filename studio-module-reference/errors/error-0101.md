---
title: "Error 0101 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0101-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0101  
 All port and parameter ID's must be unique.  
  
 This error in Azure Machine Learning occurs when one or more ports or parameters are assigned the same id value in a custom module XML definition file.  
  
## Resolution  
 Check that the id values across all ports and parameters are unique. Save the xml file, update the custom module zip package and try to add the custom module again.  
  
|Exception Messages|  
|------------------------|  
|All port and parameter IDs for a module must be unique|  
|Module '{0}' has duplicate port/argument ID's. All port/argument ID's must be unique for a module.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)