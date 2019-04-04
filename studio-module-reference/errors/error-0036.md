---
title: "Error 0036 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
## Error 0036  
 Exception occurs if multiple feature vectors were provided for a given user or item.  
  
 This error in Azure Machine Learning occurs if a feature vector is defined more than once.  
  
**Resolution :**
 Ensure that the feature vector is not defined more than once.  
  
|Exception Messages|  
|------------------------|  
|Duplicate feature definition for a user or item.|  
|Duplicate feature definition for {0}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](machine-learning-module-error-codes.md)
