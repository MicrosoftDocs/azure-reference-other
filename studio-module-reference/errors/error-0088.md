---
title: "Error 0088 | Microsoft Docs"
ms.custom: ""
ms.date: 07/19/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0088-d185d1509344
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Error 0088
**Error 0088**  
  
 Exception occurs when an invalid counting type is specified for learning with counts modules.  
  
 This error in Azure Machine Learning occurs when you try to use a  different counting method than is supported for count-based featurization.  
  
## Resolution  
 In general, counting methods are chosen from a dropdown list, so you should not see this error.  
  
 For general information, see [Learning with Counts](data-transformation-learning-with-counts.md). For requirements specific to creating and merging count-based features, see these topics:  
  
-   [Merge Count Transform](merge-count-transform.md)  
  
-   [Import Count Table](import-count-table.md)  
  
-   [Modify Count Table Parameters](modify-count-table-parameters.md)  
  
|Exception Messages|  
|------------------------|  
|Invalid counting type is specified.|  
|The specified counting type '{0}' is not a valid counting type.|  
  
 > [!TIP]
>  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
>   
>  -   [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
> -   [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See Also  
 [Module Error Codes](machine-learning-module-error-codes.md)