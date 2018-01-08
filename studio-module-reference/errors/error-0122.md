---
title: "Error 0122 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0122-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0122
**Error 0122**  
  
 Exception occurs if multiple weight columns are specified and just one is allowed.  
  
 This error in Azure Machine Learning occurs when too many columns have been selected as weight columns.  
  
## Resolution  
 Review the input dataset and its metadata. Ensure that only one column contains weights.  
  
|Exception Messages|  
|------------------------|  
|Multiple weight columns are specified.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)