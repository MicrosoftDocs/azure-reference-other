---
title: "Error 0130 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0130-d185d1509344
caps.latest.revision: 5
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0130
**Error 0130**  
  
 Exception occurs when all rows in the training dataset contain missing values.  
  
 This occurs when some column in the training dataset is empty.  
  
## Resolution  
 Use the [Clean Missing Data](../clean-missing-data.md) module to remove columns with all missing values.  
  
|Exception Messages|  
|------------------------|  
|All rows in training dataset contain missing values.  Consider using the Clean Missing Data module to remove missing values.|  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)