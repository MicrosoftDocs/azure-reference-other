---
title: "Data Transformation | Microsoft Docs"
description: "Learn about the modules in Azure Machine Learning Studio that you can use for data transformation."
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/16/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.component: "studio"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9c2844b8-7a4c-483b-848a-e35a27855716
caps.latest.revision: 14
author: ericlicoding
ms.author: amlstudiodocs
manager: cgronlun
---
# Data Transformation

This article lists the modules that are provided in Azure Machine Learning Studio for data transformation. For machine learning, *data transformation* entails some very general tasks, such as joining datasets or changing column names. But, it also includes many tasks that are specific to machine learning, such as normalization, binning and grouping, and inference of missing values.

> [!IMPORTANT]
> Data that you use in Machine Learning Studio is generally expected to be "tidy" before you import it to Machine Learning Studio. Data preparation might include, for example, ensuring that the data uses the correct encoding and checking that the data has a consistent schema.
> 
> You can use Azure Machine Learning Workbench to transform and prepare all kinds of data. For examples, see [Data transformations “by example” in Machine Learning Workbench](https://blogs.technet.microsoft.com/machinelearning/2017/09/25/by-example-transformations-in-the-azure-machine-learning-workbench/).

Modules for data transformation are grouped into the following task-based categories:
   
-   [Creating filters for digital signal processing](data-transformation-filter.md): Digital signal filters can be applied to numeric data to support machine learning tasks such as image recognition, voice recognition, and waveform analysis.
-   [Generating and using count-based features](data-transformation-learning-with-counts.md): Count-based featurization modules help you develop compact features to use in machine learning.
-   [General data manipulation and preparation](data-transformation-manipulation.md): Merging datasets, cleaning missing values, grouping and summarizing data, changing column names and data types, or indicating which column is a label or a feature.
-   [Sampling and splitting datasets](data-transformation-sample-and-split.md): Divide your data into training and test sets, split datasets by percentage or by a filter condition, or perform sampling.
-   [Scaling and reducing data](data-transformation-scale-and-reduce.md): Prepare numerical data for analysis by applying normalization or by scaling. Bin data into groups, remove or replace outliers, or perform principal component analysis (PCA).
  
##  List of modules

The following module categories are included in the **Data Transformation** category:
  
- [Data Transformation - Filter](data-transformation-filter.md)
- [Learning with Counts](data-transformation-learning-with-counts.md)
- [Data Transformation - Manipulation](data-transformation-manipulation.md)
- [Data Transformation - Sample and Split](data-transformation-sample-and-split.md)
- [Data Transformation - Scale and Reduce](data-transformation-scale-and-reduce.md)
  
## See also

- [Data Format Conversions](data-format-conversions.md)
- [Data Input and Output](data-input-and-output.md)
- [Feature Selection](feature-selection-modules.md)
- [Module categories and descriptions](machine-learning-module-descriptions.md)