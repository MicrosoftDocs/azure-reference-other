---
title: "Error 0074 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0074-d185d1509344
caps.latest.revision: 7
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0074
**Error 0074**  
  
 Exception occurs when the [Edit Metadata](../edit-metadata.md) tries to convert a sparse column to categorical.  
  
 This error in Azure Machine Learning occurs when the [Edit Metadata](../edit-metadata.md) tries to convert a sparse column to categorical.  You will receive this error when trying to convert sparse columns to categorical with the **Make categorical** option.  Azure machine Learning does not support sparse categorical arrays, so the module will fail.  
  
## Resolution  
 Make the column dense by using [Convert to Dataset](../convert-to-dataset.md) first or do not convert the column to categorical.  
  
|Exception Messages|  
|------------------------|  
|Sparse columns cannot be converted to Categorical.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)