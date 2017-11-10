---
title: "Error 0143 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 60822377-da7a-40b8-0143-d185d1509344
caps.latest.revision: 6
---
# Error 0143
**Error 0143**  
  
 Can't parse user-provided URL that is supposed to be from GitHub.  
  
 This error in Azure Machine Learning occurs when you specify an invalid URL and the module requires a valid GitHub URL.  
  
## Resolution  
 Verify that the URL refers to a valid GitHub repository. Other site types are not supported.  
  
|Exception Messages|  
|------------------------|  
|URL is not from github.com.|  
|URL is not from github.com: {0}|  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)