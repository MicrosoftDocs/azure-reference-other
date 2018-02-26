---
title: "Statistical Functions | Microsoft Docs"
description: This article describes the modules in Azure Machine Learning Studio that support mathematical and statistical operations critical for machine learning.
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/22/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 8a248cba-24aa-4779-aad6-35d73a0a2340
caps.latest.revision: 14
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Statistical Functions

This article describes the modules in Azure Machine Learning Studio that support mathematical and statistical operations critical for machine learning. If you need to perform tasks such as the following in your experiment, look in the **Statistical Functions** category:

+ Perform ad hoc computations on column values, such as rounding or using an absolute value
+ Compute means, logarithms, and other statistics commonly used in machine learning
+ Calculate correlation and probability scores
+ Compute z-scores
+ Compute dozens of different statistical distributions, such as Weibull, gamma, and beta.
+ Generate statistical reports over a set of columns or a dataset

For example, if you have a new dataset, you might use the [Summarize Data](summarize-data.md) module first. It generates a report for an entire dataset that includes standard statistical measures, such as mean and standard deviation. 

If you need more advanced statistics, such as sample skewness or interquartile distance, use the [Compute Elementary Statistics](compute-elementary-statistics.md) module to generate additional descriptive statistics.

Because the modules generate the results each time you run the experiment, the results are updated if your data changes.

## List of modules

The **Statistical Functions** category includes the following modules:  

+ [Apply Math Operation](apply-math-operation.md): Applies a mathematical operation to column values.
+ [Compute Elementary Statistics](compute-elementary-statistics.md): Calculates specified summary statistics for selected dataset columns.
+  [Compute Linear Correlation](compute-linear-correlation.md): Calculates the linear correlation between column values in a dataset.
+  [Evaluate Probability Function](evaluate-probability-function.md): Fits a specified probability distribution function to a dataset.
+ [Replace Discrete Values](replace-discrete-values.md): Replaces discrete values from one column with numeric values based on another column.
+ [Summarize Data](summarize-data.md): Generates a basic descriptive statistics report for the columns in a dataset.
+ [Test Hypothesis Using t-Test](test-hypothesis-using-t-test.md): Compares means from two datasets by using a t-test.

## See also  
- [Scale and Reduce module](data-transformation-scale-and-reduce.md)   
- [Feature Selection category](feature-selection-modules.md)   
- [Learning with Counts module](data-transformation-learning-with-counts.md)   
- [Module categories and descriptions](machine-learning-module-descriptions.md)   
- [A-Z module list](a-z-module-list.md)