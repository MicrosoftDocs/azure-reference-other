---
title: "Error 0025 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0025-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0025
**Error 0025**  
  
 Exception occurs if dataset does not contain a score column.  
  
 This error in Azure Machine Learning occurs if the input to the evaluate model does not contain valid score columns. For example, the user attempts to evaluate a dataset before it was scored with a correct trained model, or the score column was explicitly dropped upstream. This exception also occurs if the score columns on the two datasets are incompatible. For example, you might be trying to compare the accuracy of a linear regressor with that of a binary classifier.  
  
## Resolution  
 Revisit the input to the evaluate model and examine if it contains one or more score columns. If not, the dataset was not scored or the score columns were dropped in an upstream module.  
  
|Exception Messages|  
|------------------------|  
|There is no score column in dataset.|  
|There is no score column in "{0}".|  
|There is no score column in "{0}" that is produced by a "{1}". Score the dataset using the correct type of learner.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)