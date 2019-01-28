---
title: "Error 0088 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0088  
 Exception occurs when an invalid counting type is specified for learning with counts modules.  
  
 This error in Azure Machine Learning occurs when you try to use a  different counting method than is supported for count-based featurization.  
  
## Resolution  
 In general, counting methods are chosen from a dropdown list, so you should not see this error.  
  
 For general information, see [Learning with Counts](../data-transformation-learning-with-counts.md). For requirements specific to creating and merging count-based features, see these topics:  
  
-   [Merge Count Transform](../merge-count-transform.md)  
  
-   [Import Count Table](../import-count-table.md)  
  
-   [Modify Count Table Parameters](../modify-count-table-parameters.md)  
  
|Exception Messages|  
|------------------------|  
|Invalid counting type is specified.|  
|The specified counting type '{0}' is not a valid counting type.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
