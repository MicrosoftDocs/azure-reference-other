---
title: "ML Studio (classic): Data Transformation - Azure"
description: "Learn about the modules in Machine Learning Studio (classic) that you can use for data transformation."
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Data Transformation

This article lists the modules that are provided in Machine Learning Studio (classic) for data transformation. For machine learning, *data transformation* entails some very general tasks, such as joining datasets or changing column names. But, it also includes many tasks that are specific to machine learning, such as normalization, binning and grouping, and inference of missing values.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

> [!IMPORTANT]
> Data that you use in Machine Learning Studio (classic) is generally expected to be "tidy" before you import it to Machine Learning Studio (classic). Data preparation might include, for example, ensuring that the data uses the correct encoding and checking that the data has a consistent schema.
> 

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
