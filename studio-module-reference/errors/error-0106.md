---
title: "Error 0106 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0106-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0106
**Error 0106**  
  
 Thrown when a module definition file defines an unsuppported input type  
  
 This error in Azure Machine Learning is produced when the type of an input port in a custom module XML definition does not match a supported type.  
  
## Resolution  
 Make sure that the type property of an Input element in the custom module XML definition file is a supported type.  
  
|Exception Messages|  
|------------------------|  
|Unsupported input type.|  
|Unsupported input type '{0}' specified.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)