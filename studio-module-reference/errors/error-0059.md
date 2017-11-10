---
title: "Error 0059 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0059-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0059
**Error 0059**  
  
 Exception occurs if a column index specified in a column picker cannot be parsed.  
  
 This error in Azure Machine Learning occurs if a column index specified when using the Column Selector cannot be parsed.  You will receive this error when the column index is in an invalid format that cannot be parsed.  
  
## Resolution  
 Modify the column index to use a valid index value.  
  
|Exception Messages|  
|------------------------|  
|One or more specified column indexes or index ranges could not be parsed.|  
|Column index or range "{0}" could not be parsed.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)