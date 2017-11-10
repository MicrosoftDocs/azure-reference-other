---
title: "Error 0108 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0108-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0108
**Error 0108**  
  
 Thrown when a module definition file defines more input or output ports than are supported  
  
 This error in Azure Machine Learning is produced when too many input or output ports are defined in a custom module xml definition.  
  
## Resolution  
 Makes sure the maximum number of input and output ports defined in the custom module xml definition does not exceed the maximum number of supported ports.  
  
|Exception Messages|  
|------------------------|  
|Exceeded supported number of input or output ports.|  
|Exceeded number of supported '{0}' ports. Maximum allowed number of '{0}' ports is '{1}'.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)