---
title: "Error 0033 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0033-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0033  
 Exception occurs if argument is Infinity.  
  
 This error in Azure Machine Learning occurs if the argument is infinite. You will receive this error if the argument is either `double.NegativeInfinity` or `double.PositiveInfinity`.  
  
## Resolution  
 Modify the specified argument to be a valid value.  
  
|Exception Messages|  
|------------------------|  
|Argument is must be finite.|  
|"{0}" is not finite.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)