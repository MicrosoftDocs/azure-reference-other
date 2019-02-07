---
title: "Error 0087 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0087  
 Exception occurs when an invalid count table type is specified for learning with counts modules.  
  
 This error in Azure Machine Learning occurs when you try to import an existing count table, but the table is incompatible with the current data, or with the new count table.  
  
## Resolution  
 There are different formats for saving the counts and rules that make up the transformation. If you are merging count tables, verify that both use the same format.  
  
 Generally, a count-based transform can only be applied to datasets that have the same schema as the dataset on which the transform was originally created.  
  
 For general information, see [Learning with Counts](../data-transformation-learning-with-counts.md). For requirements specific to creating and merging count-based features, see these topics:  
  
-   [Merge Count Transform](../merge-count-transform.md)  
  
-   [Import Count Table](../import-count-table.md)  
  
-   [Modify Count Table Parameters](../modify-count-table-parameters.md)  
  
|Exception Messages|  
|------------------------|  
|Invalid count table type is specified.|  
|The specified count table type '{0}' is not a valid count table type.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
