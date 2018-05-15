---
title: "Error 0034 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0034-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0034  
 Exception occurs if more than one rating exists for a given user-item pair.  
  
 This error in Azure Machine Learning occurs in recommendation if a user-item pair has more than one rating value.  
  
## Resolution  
 Ensure that the user-item pair possesses one rating value only.  
  
|Exception Messages|  
|------------------------|  
|More than one rating exist for the value(s) in dataset.|  
|More than one rating for user {0} and item {1} in rating prediction data table.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)