---
title: "Error 0061 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0061-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0061
**Error 0061**  
  
 Exception occurs when attempting to add a row to a DataTable that has a different number of columns than the table.  
  
 This error in Azure Machine Learning occurs when you attempt to add a row to a dataset that has a different number of columns than the dataset.  You will receive this error if the row that is being added to the dataset has a different number of columns from the input dataset.  The row cannot be appended to the dataset if the number of columns is different.  
  
## Resolution  
 Modify the input dataset to have the same number of columns as the row added, or modify the row added to have the same number of columns as the dataset.  
  
|Exception Messages|  
|------------------------|  
|All tables must have the same number of columns.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](../machine-learning-module-error-codes.md)