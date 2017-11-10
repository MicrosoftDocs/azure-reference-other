---
title: "Error 0151 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 60822377-da7a-40b8-0151-d185d1509344
caps.latest.revision: 7
---
# Error 0151
**Error 0151**  
  
 There was an error writing to cloud storage. Please check the URL.  
  
 This error in Azure Machine Learning occurs when the module tries to write data to cloud storage but the URL is unavailable or invalid.  
  
## Resolution  
 Check the URL and verify that it is writable.  
  
|Exception Messages|  
|------------------------|  
|Error writing to cloud storage (possibly a bad url).|  
|Error writing to cloud storage: {0}. Please check the url.|  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)