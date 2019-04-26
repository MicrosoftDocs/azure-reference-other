---
title: "Linear Discriminant Analysis (deprecated) | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.date: 01/24/2018
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Linear Discriminant Analysis (deprecated)

*Identify a linear set of variables that best separates two or more classes*

Category: [Feature Selection Modules](feature-selection-modules.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Fisher Linear Discriminant Analysis** module in Azure Machine Learning Studio, to create a set of scores that identifies the combination of features that best separate two or more classes.  

You provide a set of possible feature columns as inputs, and the algorithm determines the optimal combination of the input columns that linearly separates each group of data while minimizing the distances within each group.  

> [!WARNING]
> This module is provided solely for backward compatibility with experiments created using the pre-release version of Azure Machine Learning. We recommend that you modify your experiments to use [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) instead.

### More about linear discriminant analysis

Linear discriminant analysis is often used for dimensionality reduction, because it projects a set of features onto a smaller feature space while preserving the information that discriminates between classes. This not only reduces computational costs for a given classification task, but can help prevent overfitting.

Linear discriminant analysis is similar to analysis of variance (ANOVA) in that it works by comparing the means of the variables, and is based on these assumptions:

+ Predictors are independent

+ Values are normally distributed

+ Variances among groups are similar

Linear Discriminant Analysis is sometimes abbreviated to LDA, but this is easily confused with Latent Dirichlet Allocation. The techniques are completely different.

## How to use Linear Discriminant Analysis

1. Add the **Linear Discriminant Analysis** module to your experiment in Studio, and connect the dataset you want to evaluate.

2. Select a set of numeric feature columns as inputs. The columns provided as inputs must meet these requirements:

    + Your data must be complete (no missing values).
    + It is also useful to have fewer predictors than there are samples.
    + Because the values are expected to have a normal distribution, you should review the data for outliers.

3. Run the experiment.

    The algorithm determines the optimal combination of the input columns that linearly separates each group of data while minimizing the distances within each group.

### Results

The module has two outputs:

+ **Feature Extractors**: A set of scores (eigenvectors), also called a discrimination matrix.

+ **Transformed Features**: A dataset containing the features that have been transformed using the eigenvectors.

## Examples

To see examples of how feature selection is used in machine learning experiments, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):

+ [Twitter Sentiment Analysis](http://go.microsoft.com/fwlink/?LinkId=525274): Uses filter-Based Feature Selection to improve experiment results.

+ [Fisher Linear Discriminant Analysis](https://gallery.cortanaintelligence.com/Details/35da9465c13f4050babff2f297284dc1): Demonstrates how to use this module for dimensionality reduction.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

+ This method works only on continuous variables, not categorical or ordinal variables.

+ Rows with missing values are ignored when computing the transformation matrix.

+ The algorithm will examine all numeric columns not designated as labels, to see if there is any correlation. If you want to exclude a numeric column, add a [Select Columns in Dataset](select-columns-in-dataset.md) module before feature selection to create a view that contains only the columns you wish to analyze.

### Related research

For more information about how the eigenvalues are calculated, see this paper (PDF download):

+ [Eigenvector-based Feature Extraction for Classification](http://www.aaai.org/Papers/FLAIRS/2002/FLAIRS02-070.pdf). Tymbal, Puuronen et al.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Class labels column|any|ColumnSelection|None|Select the column that contains the categorical class labels|  
  
## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Feature extractors|[Data Table](data-table.md)|Eigen vectors of input dataset|  
|Transformed features|[Data Table](data-table.md)|Fisher linear discriminant analysis features transformed to eigen vector space|

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|

For a list of errors specific to Studio modules, see [Machine Learning Error codes](/errors/machine-learning-module-error-codes.md)

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [Deprecated Modules and Features](deprecated-modules-and-features.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)
