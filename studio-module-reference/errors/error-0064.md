---
title: "Error 0064 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0064  
 Exception occurs if Azure storage account name or storage key is specified incorrectly.  
  
 This error in Azure Machine Learning occurs if the Azure storage account name or storage key is specified incorrectly. You will receive this error if you enter an incorrect account name or password for the storage account. This may occur if you manually enter the account name or password. It may also occur if the account has been deleted.  
  
## Resolution  
 Verify that the account name and password have been entered correctly, and that the account exists.  
  
|Exception Messages|  
|------------------------|  
|The Azure storage account name or storage key is incorrect.|  
|The Azure storage account name "{0}" or storage key for the account name is incorrect.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
