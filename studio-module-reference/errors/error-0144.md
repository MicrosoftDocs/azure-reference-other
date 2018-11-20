---
title: "Error 0144 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 60822377-da7a-40b8-0144-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0144  
 User-provided GitHub url is missing the expected part.  
  
 This error in Azure Machine Learning occurs when you specify a GitHub file source using an invalid URL format.  
  
## Resolution  
 Check that the URL of the GitHub repository is valid and ends with \blob\ or \tree\\.  
  
|Exception Messages|  
|------------------------|  
|Cannot parse GitHub URL.|  
|Cannot parse GitHub URL (expecting '\blob\\' or '\tree\\' after the repository name): {0}|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)