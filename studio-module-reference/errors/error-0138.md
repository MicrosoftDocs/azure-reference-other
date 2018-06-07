---
title: "Error 0138 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 07/19/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 60822377-da7a-40b8-0138-d185d1509344
caps.latest.revision: 6
author: rastala
ms.author: roastala
manager: cgronlun
---
# Error 0138  
 Memory has been exhausted, unable to complete running of module. Downsampling the dataset may help to alleviate the problem.  
  
 This error occurs when the module that is running requires more memory than is available in the Azure container. This can happen if you are working with a very large dataset and the current operation cannot fit into memory.  
  
## Resolution  
 If you are trying to read a very large dataset and the operation cannot be completed, downsampling the dataset might help.  
  
 If you use the visualizations on datasets to check the cardinality of columns, only some rows are sampled. To get a full report, use [Summarize Data](../summarize-data.md). You can also use the [Apply SQL Transformation](../apply-sql-transformation.md) to check for the number of unique values in each column.  
  
 Sometimes transient loads can lead to this error. Machine support also changes over time. See the [Azure Machine Learning FAQ](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/) for  a description of supported data size.  
  
 Try using [Principal Component Analysis](../principal-component-analysis.md) or one of the provided feature selection methods to reduce your dataset to a smaller set of more feature-rich columns: [Feature Selection](../feature-selection-modules.md)  
  
|Exception Messages|  
|------------------------|  
|Memory has been exhausted, unable to complete running of module.|  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)