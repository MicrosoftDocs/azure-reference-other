---
title: "Error 0134 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0134-d185d1509344
caps.latest.revision: 5
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0134
**Error 0134**  
  
 Exception occurs when label column is missing or has insufficient number of labeled rows.  
  
 This error occurs when the module requires a label column, but you did not include one in the column selection, or the label column has too many missing values.  
  
## Resolution  
 If you included a label column in the column selection but it isn’t being recognized, use the [Edit Metadata](edit-metadata.md) module to mark it as a label column.  
  
 Use the [Clean Missing Data](clean-missing-data.md) module to remove rows that don’t have a value in the label column. You can also use the [Summarize Data](summarize-data.md) module to find out how many values are missing in each column.  
  
|Exception Messages|  
|------------------------|  
|Exception occurs when label column is missing or has insufficient number of labeled rows.|  
|Exception occurs when label column is missing or has less than {0} labeled rows|  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)