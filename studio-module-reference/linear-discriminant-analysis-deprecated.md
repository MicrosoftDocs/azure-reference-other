---
title: "Linear Discriminant Analysis (deprecated) | Microsoft Docs"
ms.custom: ""
ms.date: 07/01/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f83ba3fb-6680-442c-89b6-db418b53264c
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Linear Discriminant Analysis (deprecated)
*Identify a linear set of variables that best separates two or more classes*  
  
 Category: [Feature Selection Modules](feature-selection-modules.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use **Fisher Linear Discriminant Analysis** to create a set of scores that identifies the combination of features that best separate two or more classes.  
  
> [!WARNING]
>  This module is provided for backward compatibility with experiments created using the pre-release version of Azure Machine Learning, and will soon be deprecated. We recommend that you modify your experiments to use [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) instead.  
  
 Linear discriminant analysis is often used for dimensionality reduction, because it projects a set of features onto a smaller feature space while preserving the information that discriminates between classes. This not only reduces computational costs for a given classification task, but can help prevent overfitting.  
  
 You provide a set of possible feature columns as inputs, and the algorithm determines the optimal combination of the input columns that linearly separates each group of data while minimizing the distances within each group.  
  
 Linear discriminant analysis is similar to analysis of variance (ANOVA) in that it works by comparing the means of the variables, and is based on these assumptions:  
  
-   Predictors are independent  
  
-   Values are normally distributed  
  
-   Variances among groups are similar  
  
 Note that Linear Discriminant Analysis is sometimes abbreviated to LDA, but this is easily confused with Latent Dirichlet Allocation. The techniques are completely different, so in this documentation, the acronym LDA will be used only for Latent Dirichlet Allocation.  
  
## How to Use Linear Discriminant Analysis  
  
1.  After connecting your dataset, select a set of numeric feature columns as inputs.  
  
     The columns provided as inputs must meet these requirements:  
  
    -   Your data must be complete (no missing values).  
  
    -   It is also useful to have fewer predictors than there are samples  
  
    -   Because the values are expected to have a normal distribution, you should review the data for outliers.  
  
2.  The algorithm determines the optimal combination of the input columns that linearly separates each group of data while minimizing the distances within each group.  
  
## Examples  
 To see examples of how feature selection is used in machine learning experiments, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Twitter Sentiment Analysis](http://go.microsoft.com/fwlink/?LinkId=525274) sample uses filter-Based Feature Selection to improve experiment results.  
  
-   The [Fisher Linear Discriminant Analysis](https://gallery.cortanaintelligence.com/Details/35da9465c13f4050babff2f297284dc1) sample demonstrates how to use this module for dimensionality reduction.  
  
##  <a name="Notes"></a> Technical Notes  
  
-   This method works only on continuous variables, not categorical or ordinal variables.  
  
-   Rows with missing values are ignored when computing the transformation matrix.  
  
-   The algorithm will examine all numeric columns not designated as labels, to see if there is any correlation. If you want to exclude a numeric column, add a [Select Columns in Dataset](select-columns-in-dataset.md) module before feature selection to create a view that contains only the columns you wish to analyze.  
  
### Interpreting the Output  
 The module has two outputs:  
  
-   Feature Extractors  
  
     A set of scores (eigenvectors), also called a discrimination matrix.  
  
-   Transformed Features  
  
     A dataset containing the features that have been transformed using the eigenvectors.  
  
 For example, the following table shows the output when [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) was performed on a subset of features from the [Breast Cancer](http://go.microsoft.com/fwlink/?LinkId=525726) sample dataset:  
  
|E1|E2|E3|E4|  
|--------|--------|--------|--------|  
|0.997588|0.97843|0.982406|-0.937945|  
|0.055731|-0.163812|-0.104849|-0.174996|  
|0.0411289|-0.115274|0.103606|0.257335|  
|0.0046382|0.0504354|-0.114674|0.153015|  
  
 These values represent four eigenvectors for each of the predictors (deg-malig, node-caps, tumor-size, breast-quad), and their associated eigenvalues. The combination of eigenvectors and their values provides information about the shape of the linear transformation.  
  
 In general, bigger scores (farther from zero) are better predictors. When deciding which combination of variables to keep for the optimal (and smaller) dimensional subspace, you can eliminates the eigenvectors with the lowest values, because they contain the least information about the distribution of the data.  
  
 In this example, the values in the eigenvectors all have a similar magnitude, which indicates that the data is projected onto a fairly good feature space.  
  
 However, if some of the eigenvalues were much larger than others, you would want to keep only those eigenvectors with the highest values, since they contain more information about the data distribution. That is, values that are closer to 0 are less informative and should be dropped when selecting a new set of features.  
  
 For more information about how the eigenvalues are calculated, see this paper (PDF):  
  
 [Eigenvector-based Feature Extraction for Classification](http://www.aaai.org/Papers/FLAIRS/2002/FLAIRS02-070.pdf). Tymbal, Puuronen et al.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Class labels column|any|ColumnSelection|None|Select the column that contains the categorical class labels|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Feature extractors|[Data Table](data-table.md)|Eigen vectors of input dataset|  
|Transformed features|[Data Table](data-table.md)|Fisher linear discriminant analysis features transformed to eigen vector space|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0017](error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  
  
## See Also  
 [Deprecated Modules and Features](deprecated-modules-and-features.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)