---
title: "Error 0086 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 08/15/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0086-d185d1509344
caps.latest.revision: 8
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0086  
 Exception occurs when a counting transform is invalid.  
  
 This error in Azure Machine Learning occurs when you select a transformation based on a count table, but the selected transform is incompatible with the current data, or with the new count table.  
  
## Resolution  
 The module supports saving the counts and rules that make up the transformation in two different formats. If you are merging count tables, verify that both tables you intend to merge use the same format.  
  
 Also, note that in general, a count-based transform can only be applied to datasets that have the same schema as the dataset on which the transform was originally created.  
  
 For general information, see [Learning with Counts](../data-transformation-learning-with-counts.md). For requirements specific to creating and merging count-based features, see these topics:  
  
-   [Merge Count Transform](../merge-count-transform.md)  
  
-   [Import Count Table](../import-count-table.md)  
  
-   [Modify Count Table Parameters](../modify-count-table-parameters.md)  
  
|Exception Messages|  
|------------------------|  
|Invalid counting transform specified.|  
|The counting transform at input port '{0}' is invalid.|  
|The counting transform at input port '{0}' cannot be merged with the counting transform at input port '{1}'. Please check to verify the metadata used for counting matches.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)