---
title: "Error 0081 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0081-d185d1509344
caps.latest.revision: 7
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0081
**Error 0081**  
  
 Exception occurs in PCA module if number of dimensions to reduce to is equal to number of feature columns in input dataset, containing at least one sparse feature column.  
  
 This error in Azure Machine Learning is produced if the following conditions are met: (a) the input dataset has at least one sparse column and (b) the final number of dimensions requested is the same as the number of input dimensions.  
  
## Resolution  
 Consider reducing the number of dimensions in the output to be fewer than the number of dimensions in the input. This is typical in applications of PCA.  For more information, see [Principal Component Analysis](../principal-component-analysis.md).  
  
|Exception Messages|  
|------------------------|  
|For dataset containing sparse feature columns number of dimensions to reduce to should be less than number of feature columns.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)