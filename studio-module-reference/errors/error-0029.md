---
title: "Error 0029 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0029-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0029
**Error 0029**  
  
 Exception occurs in case when invalid URI is passed.  
  
 This error in Azure Machine Learning occurs in case when invalid URI is passed.  You will receive this error if any of the following is true:, or.  
  
-   The Public or SAS URI provided for Azure Blob Storage for read or write contains an error.  
  
-   The time window for the SAS has expired.  
  
-   The Web URL via HTTP source represents a file or a loopback URI.  
  
-   The Web URL via HTTP contains an incorrectly formatted URL.  
  
-   The URL cannot be resolved by the remote source.  
  
## Resolution  
 Revisit the module and verify the format of the URI. If the data source is a Web URL via HTTP, verify that the intended source is neither a file nor a loopback URI (localhost).  
  
|Exception Messages|  
|------------------------|  
|Invalid Uri is passed.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)