---
title: "Data Transformation - Scale and Reduce | Microsoft Docs"
description: "Learn about the Azure Machine Learning Studio modules that can help you work with numerical data."
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 345c5ed4-4dd6-4998-9773-6ca0e00e6946
caps.latest.revision: 16
author: rastala
ms.author: amlstudiodocs
manager: cgronlun
---
# Data Transformation - Scale and Reduce

This article describes the modules in Azure Machine Learning Studio that can help you work with numerical data. For machine learning, common data tasks include clipping, binning, and normalizing numerical values. Other modules support dimensionality reduction.

## Modeling numerical data

Tasks such as normalizing, binning, or redistributing numerical variables are an important part of data preparation for machine learning. The modules in this group support the following data preparation tasks:

- Grouping data into bins of varying sizes or distributions.
- Removing outliers or changing their values.
- Normalizing a set of numeric values into a specific range.
- Creating a compact set of feature columns from a high-dimension dataset.

## Related tasks

- Select relevant and useful features to use in building the model: Use the [Feature Selection](feature-selection-modules.md) or [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) modules.
- Select features based on counts of the values: Use the [Learning with Counts](data-transformation-learning-with-counts.md) module.
- Remove or replace missing values: Use the [Clean Missing Data](clean-missing-data.md) module.
- Replace categorical values with numerical values that are derived from calculations: Use the [Replace Discrete Values](replace-discrete-values.md) module.
- Compute a probability distribution for discrete or numerical columns: Use the [Evaluate Probability Function](evaluate-probability-function.md) module.
- Filter and transform digital signals and waveforms: Use the [Filter](data-transformation-filter.md) module.

## List of modules

This **Data Transformation - Scale and Reduce** category includes the following modules:

- [Clip Values](clip-values.md): Detects outliers, and then clips or replaces their values.
- [Group Data into Bins](group-data-into-bins.md): Puts numerical data into bins.
- [Normalize Data](normalize-data.md): Rescales numeric data to constrain dataset values to a standard range.
- [Principal Component Analysis](principal-component-analysis.md): Computes a set of features that have reduced dimensionality for more efficient learning.

## See also

- [Manipulation](data-transformation-manipulation.md)
- [Sample and Split](data-transformation-sample-and-split.md)
- [Filter](data-transformation-filter.md)
- [Learning with Counts](data-transformation-learning-with-counts.md)
- [Feature Selection](feature-selection-modules.md)
- [Module categories and descriptions](machine-learning-module-descriptions.md)
- [A-Z module list](a-z-module-list.md)
