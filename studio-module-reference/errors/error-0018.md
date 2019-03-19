---
title: "Error 0018 | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 07/19/2016
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Error 0018  
 Exception occurs if input dataset is not valid.  
  
## Resolution  
 This error in Azure Machine Learning can appear in many contexts, so there is not a single resolution. In general, the error indicates that the data provided as input to a module has the wrong number of columns, or that the data type does not match requirements of the module. For example:  
  
-   The module requires a label column, but no column is marked as a label, or you have not selected a label column yet.  
  
-   The module requires that data be categorical but your data is numeric.  
  
-   The module requires a specific data type. For example, ratings provided to [Train Matchbox Recommender](../train-matchbox-recommender.md) can be either numeric or categorical, but cannot be floating point numbers.  
  
-   The data is in the wrong format.  
  
-   Imported data contains invalid characters, bad values, or out of range values.  
  
-   The column is empty or contains too many missing values.  
  
 To determine the requirements and how your data might, review the help topic for the module that will be consuming the dataset as input.  
  
 We also recommend that you use [Summarize Data](../summarize-data.md) or [Compute Elementary Statistics](../compute-elementary-statistics.md) to profile your data, and use these modules to fix metadata and clean values: [Edit Metadata](../edit-metadata.md), [Clean Missing Data](../clean-missing-data.md), [Clip Values](../clip-values.md).  
  
|Exception Messages|  
|------------------------|  
|Dataset is not valid.|  
|{0} contains invalid data.|  
|{0} and {1} should be consistent columnwise.|  
  
 > [!TIP]
 >  Need more help or troubleshooting tips for Azure Machine Learning? Try these resources:  
 >  
 >  -  [Troubleshooting guide: Create and connect to an Machine Learning workspace](https://azure.microsoft.com/documentation/articles/machine-learning-troubleshooting-creating-ml-workspace/)  
 >  -  [Azure Machine Learning Frequently Asked Questions (FAQ)](https://azure.microsoft.com/documentation/articles/machine-learning/studio/faq/)  
  
## See also  
 [Module error codes](../machine-learning-module-error-codes.md)
