---
title: "Error 0047 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0047-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0047
**Error 0047**  
  
 Exception occurs if number of feature columns in some of the datasets passed to the module is too small.  
  
 This error in Azure Machine Learning occurs if the input dataset to training does not contain the minimum number of columns required by the algorithm. Typically either the dataset is empty or only contains training columns.  
  
## Resolution  
 Revisit the input dataset to make sure there one or more additional columns apart from the label column.  
  
|Exception Messages|  
|------------------------|  
|Number of feature columns in input dataset is less than allowed minimum.|  
|Number of feature columns in input dataset is less than allowed minimum of {0} column(s).|  
|Number of feature columns in input dataset "{0}" is less than allowed minimum of {1} column(s).|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)