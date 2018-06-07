---
title: "Error 0023 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0023-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0023  
 Exception occurs if target column of input dataset is not valid for the current trainer module.  
  
 This error in Azure Machine Learning  occurs if the target column (as selected in the module parameters) is not of the valid data-type, contained all missing values, or was not categorical as expected.  
  
## Resolution  
 Revisit the module input to inspect the content of the label/target column. Make sure it does not have all missing values. If the module is expecting target column to be categorical, make sure that there are more than one distinct values in the target column.  
  
|Exception Messages|  
|------------------------|  
|Input dataset has unsupported target column.|  
|Input dataset has unsupported target column "{0}".|  
|Input dataset has unsupported target column "{0}" for learner of type {1}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)