---
title: "Error 0066 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0066-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0066  
 Exception occurs if a resource could not be uploaded to an Azure Blob.  
  
 This error in Azure Machine Learning occurs if a resource could not be uploaded to an Azure Blob. You will receive this message if [Train Vowpal Wabbit 7-4 Model](../train-vowpal-wabbit-version-7-4-model.md) encounters an error attempting to save either the model or the hash created when training the model. Both are saved to the same Azure storage account as the account containing the input file.  
  
## Resolution  
 Revisit the module. Verify that the Azure account name, storage key, and container are correct and that the account has permission to write to the container.  
  
|Exception Messages|  
|------------------------|  
|The resource could not be uploaded to Azure storage.|  
|The file "{0}" could not be uploaded to Azure storage as {1}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)