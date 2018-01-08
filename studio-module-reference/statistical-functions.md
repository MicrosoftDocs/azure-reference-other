---
title: "Statistical Functions | Microsoft Docs"
ms.custom: ""
ms.date: 09/21/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8a248cba-24aa-4779-aad6-35d73a0a2340
caps.latest.revision: 14
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Statistical Functions
This article describes a group of modules in Azure Machine Learning that support mathematical and statistical operations critical for machine learning. Modules in the **Statistical Functions** group perform tasks such as these, when added to a machine learning experiment:  
  
+ Perform ad hoc computations on column values, including rounding. Compute means, logarithms, and other statistics commonly used in machine learning.  
+   Calculate correlations among columns.  
+ Generate probability scores for column values. 
+ Calculate z scores for multiple test types and sample sizes.
+ Test the values in a column against a variety of statistical distributions.  
+   Generate statistical reports that summarize a set of columns or a complete dataset.  

    For example, the [Summarize Data](summarize-data.md) module generates a report for an entire dataset that includes standard statistical measures such as mean and standard deviation. 
    
    Using the [Compute Elementary Statistics](compute-elementary-statistics.md) module, you can generate additional descriptive statistics, such as sample skewness or   interquartile distance.
  

  
##  <a name="modules"></a> List of Modules
  
 The **Statistical Functions** category includes the following modules:  
  
|Module|Description|  
|------------|-----------------|  
|[Apply Math Operation](apply-math-operation.md)|Applies a mathematical operation to column values|  
|[Compute Elementary Statistics](compute-elementary-statistics.md)|Calculates specified summary statistics for selected dataset columns|  
|[Compute Linear Correlation](compute-linear-correlation.md)|Calculates the linear correlation between column values in a dataset|  
|[Evaluate Probability Function](evaluate-probability-function.md)|Fits a specified probability distribution function to a dataset|  
|[Replace Discrete Values](replace-discrete-values.md)|Replaces discrete values from one column with numeric values based on another column|  
|[Summarize Data](summarize-data.md)|Generates a basic descriptive statistics report for the columns in a dataset|  
|[Test Hypothesis Using t-Test](test-hypothesis-using-t-test.md)|Compares means from two datasets using a t-test|  
  
## See Also  
 [Scale and Reduce](data-transformation-scale-and-reduce.md)   
 [Feature Selection](feature-selection-modules.md)   
 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [A-Z Module List](a-z-module-list.md)