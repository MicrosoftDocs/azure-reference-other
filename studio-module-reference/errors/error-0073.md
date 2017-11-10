---
title: "Error 0073 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0073-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0073
**Error 0073**  
  
 Exception occurs if an error occurs while converting a column to another type.  
  
 This error in Azure Machine Learning occurs when it is not possible to convert column to another type.  You will receive this error if a module requires a particular type and it is not possible to convert the column to the new type.  
  
## Resolution  
 Modify the input dataset so that the column can be converted based on the inner exception.  
  
|Exception Messages|  
|------------------------|  
|Failed to convert column.|  
|Failed to convert column to {0}.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)