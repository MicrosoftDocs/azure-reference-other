---
title: "Error 0079 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0079-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0079
**Error 0079**  
  
 Exception occurs if Azure storage container name is specified incorrectly.  
  
 This error in Azure Machine Learning occurs if the Azure storage container name is specified incorrectly. You will receive this error if you have not specified both the container and the blob (file) name using **the Path to blob beginning with container** option when writing to Azure Blob Storage.  
  
## Resolution  
 Revisit the [Export Data](../export-data.md) module and verify that the specified path to the blob contains both the container and the file name, in the format **container/filename**.  
  
|Exception Messages|  
|------------------------|  
|The Azure storage container name is incorrect.|  
|The Azure storage container name "{0}" is incorrect; a container name of the format container/blob was expected.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)