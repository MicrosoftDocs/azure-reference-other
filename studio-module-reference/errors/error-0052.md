---
title: "Error 0052 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0052-d185d1509344
caps.latest.revision: 8
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0052  
 Exception occurs if Azure storage account key is specified incorrectly.  
  
 This error in Azure Machine Learning occurs if the key used to access the Azure storage account is incorrect. For example, you might see this error if the Azure storage key was truncated when copied and pasted, or if the wrong key was used.  
  
 For more information about how to get the key for an Azure storage account, see [View, copy, and regenerate storage access keys](https://azure.microsoft.com/documentation/articles/storage-create-storage-account-classic-portal/).  
  
## Resolution  
 Revisit the module and verify that the Azure storage key is correct for the account; copy the key again from the Azure classic portal if necessary.  
  
|Exception Messages|  
|------------------------|  
|The Azure storage account key is incorrect.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)