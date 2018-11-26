---
title: "Error 0067 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0067-d185d1509344
caps.latest.revision: 6
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0067  
 Exception occurs if a dataset has a different number of columns than expected.  
  
 This error in Azure Machine Learning occurs if a dataset has a different number of columns than expected.  You will receive this error when the number of columns in the dataset are different from the number of columns that the module expects during execution.  
  
## Resolution  
 Modify the input dataset or the parameters.  
  
|Exception Messages|  
|------------------------|  
|Unexpected number of columns in the datatable.|  
|Expected "{0}" columns but found "{1}" columns instead.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)