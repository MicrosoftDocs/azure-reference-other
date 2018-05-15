---
title: "Error 0030 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0030-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0030  
 Exception occurs in the case when it is not possible to download a file.  
  
 This exception in Azure Machine Learning occurs when it is not possible to download a file. You will receive this exception when an attempted read from an HTTP source has failed after three (3) retry attempts.  
  
## Resolution  
 Verify that the URI to the HTTP source is correct and that the site is currently accessible via the Internet.  
  
|Exception Messages|  
|------------------------|  
|Unable to download a file.|  
|Error while downloading the file: {0}.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)