---
title: "ML Studio (classic): Fisher Linear Discriminant Analysis - Azure"
description: Learn how to use the Fisher Linear Discriminant Analysis module to create a new feature that captures the combination of features that best separates two or more classes.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Fisher Linear Discriminant Analysis

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Identifies the linear combination of feature variables that can best group data into separate classes*

Category: [Feature Selection Modules](feature-selection-modules.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Fisher Linear Discriminant Analysis** module in Machine Learning Studio (classic), to create a new feature dataset that captures the combination of features that best separates two or more classes.

This method is often used for dimensionality reduction, because it projects a set of features onto a smaller feature space while preserving the information that discriminates between classes. This not only reduces computational costs for a given classification task, but can help prevent overfitting.

To generate the scores, you provide a label column and set of numerical feature columns as inputs. The algorithm determines the optimal combination of the input columns that linearly separates each group of data while minimizing the distances within each group. The module returns a dataset containing the compact, transformed features, along with a transformation that you can save and apply to another dataset.

### More about linear discriminant analysis

Linear discriminant analysis is similar to analysis of variance (ANOVA) in that it works by comparing the means of the variables. Like ANOVA, it relies on these assumptions:

- Predictors are independent
- The conditional probability density functions of each sample are normally distributed
- Variances among groups are similar

Linear Discriminant Analysis is sometimes abbreviated to LDA, but this is easily confused with *Latent Dirichlet Allocation*. The techniques are completely different, so in this documentation, we use the full names wherever possible.

## How to configure Linear Discriminant Analysis

1. Add your input dataset and check that the input data meets these requirements:

    - Your data should be as complete as possible. Rows with any missing values are ignored.
    - Values are expected to have a normal distribution.  Before using **Fisher Linear Discriminant Analysis**,  review the data for outliers, or test the distribution.
    - You should have fewer predictors than there are samples.
    - Remove any non-numeric columns. The algorithm examines **all** valid numeric columns included in the inputs, and return an error if invalid columns are included. If you need to exclude any numeric columns, add a [Select Columns in Dataset](select-columns-in-dataset.md) module before **Fisher Linear Discriminant Analysis**, to create a view that contains only the columns you wish to analyze. You can rejoin the columns later using [Add Columns](add-columns.md). The original order of rows is preserved.

2. Connect the input data to the **Fisher Linear Discriminant Analysis** module.

3. For **Class labels column**, click **Launch column selector** and choose one label column.

4. For **Number of feature extractors**, type the number of columns that you want as a result.

    For example, if your dataset contains eight numeric feature columns, you might type `3` to collapse them into a new, reduced feature space of only three columns.

    It is important to understand that the output columns do not correspond exactly to the input columns, but rather represent a compact transformation of the values in the input columns.

    If you use 0 as the value for **Number of feature extractors**, and _n_ columns are used as input, _n_ feature extractors are returned, containing new values representing the n-dimensional feature space.

5. Run the experiment.

### Results

The algorithm determines the combination of values in the input columns that linearly separates each group of data while minimizing the distances within each group, and creates two outputs:

- **Transformed features**. A dataset containing the specified number of feature extractor columns, named **col1**, **col2**, **col3**, and so forth. The output also includes the class or label variable as well.

    You can use this compact set of values for training a model.

- **Fisher linear discriminant analysis transformation**. A transformation that you can save and then apply to a dataset that has the same schema. This is useful if you are analyzing many datasets of the same type and want to apply the same feature reduction to each. The dataset that you apply it to should have the same schema.

## Examples

For examples of feature selection in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai):

- [Fisher Linear Discriminant Analysis](https://gallery.azure.ai/Experiment/Fis-her-Linear-Discriminant-Analysis-and-Apply-Transformation-2): Demonstrates how to use this module for dimensionality reduction.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

- This method works only on continuous variables, not categorical or ordinal variables.

- Rows with missing values are ignored when computing the transformation matrix.

- If you save a transformation from an experiment, the transformations computed from the original experiment are reapplied to each new set of data, and are not recomputed. Therefore, if you want to compute a new feature set for each set of data, use a new instance of **Fisher Linear Discriminant Analysis** for each dataset.

### Implementation details

The dataset of features is transformed using *eigenvectors*. The eigenvectors for the input dataset are computed based on the provided feature columns, also called a *discrimination matrix*.

The transformation output by the module contains these eigenvectors, which can be applied to transform another dataset that has the same schema.

For more information about how the eigenvalues are calculated, see this paper (PDF): [Eigenvector-based Feature Extraction for Classification](https://www.aaai.org/Papers/FLAIRS/2002/FLAIRS02-070.pdf). Tymbal, Puuronen et al.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  

## Module parameters

|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Class labels column|ColumnSelection||Required|None|Select the column that contains the categorical class labels|  
|Number of feature extractors|Integer|>=0|Required|0|Number of feature extractors to use. If zero, then all feature extractors will be used|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Transformed features|[Data Table](data-table.md)|Fisher linear discriminant analysis features transformed to eigenvector space|  
|Fisher linear discriminant analysis transformation|[ITransform interface](itransform-interface.md)|Transformation of Fisher linear discriminant analysis| 

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Feature Selection](feature-selection-modules.md)   
 [Filter Based Feature Selection](filter-based-feature-selection.md)   
 [Principal Component Analysis](principal-component-analysis.md)
