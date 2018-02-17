---
title: "Data Transformation - Scale and Reduce | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 345c5ed4-4dd6-4998-9773-6ca0e00e6946
caps.latest.revision: 16
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Data Transformation - Scale and Reduce

This article describes the modules in Azure Machine Learning Studio that are provided to help you work with numerical data. For machine learning, common data tasks include clipping, binning, and normalizing numerical values. Other modules support dimensionality reduction.  
  
## Modeling numerical data

Tasks such as normalizing, binning, or redistributing numerical variables are an important part of data preparation for machine learning. The modules in this group support the following data preparation tasks:  
  
-   Grouping data into bins of varying sizes or distributions  
  
-   Removing outliers or changing their values  
  
-   Normalizing a set of numeric values into a specific range  
  
-   Creating a compact set of feature columns from a high-dimension dataset  
  
## Related tasks  

In addition to these modules, you might find the following related tools useful for transforming numeric data:  
  
- Selecting the relevant and useful features for use in building the model: [Feature Selection](feature-selection-modules.md) or [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)  
  
- Selecting features based on counts of the values: [Learning with Counts](data-transformation-learning-with-counts.md)  
  
- Removing or replacing missing values: [Clean Missing Data](clean-missing-data.md)  
  
- Replacing categorical values with numerical values derived from calculations: [Replace Discrete Values](replace-discrete-values.md)  
  
- Computing a probability distribution for discrete or numerical columns: [Evaluate Probability Function](evaluate-probability-function.md)  
  
- Filtering and transforming digital signals and waveforms: [Filter](data-transformation-filter.md)  
  
##  List of modules  

The following table lists the modules in this category:  
  
|Module|Description|  
|------------|-----------------|  
|[Clip Values](clip-values.md)|Detects outliers and clips or replaces their values|  
|[Group Data into Bins](group-data-into-bins.md)|Puts numerical data into bins|  
|[Normalize Data](normalize-data.md)|Rescales numeric data to constrain dataset values to a standard range|  
|[Principal Component Analysis](principal-component-analysis.md)|Computes a set of features with reduced dimensionality for more efficient learning|  

## See also  
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [Manipulation](data-transformation-manipulation.md)   
 [Sample and Split](data-transformation-sample-and-split.md)   
 [Filter](data-transformation-filter.md)   
 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Feature Selection](feature-selection-modules.md)   
 [A-Z Module List](a-z-module-list.md)