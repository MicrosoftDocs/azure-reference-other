---
title: "Machine Learning Modules | Microsoft Docs"
ms.custom: ""
ms.date: 10/13/2015
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6d9e2516-1343-4859-a3dc-9673ccec9edc
caps.latest.revision: 13
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Machine Learning Modules
The typical workflow for machine learning includes many phases:  
  
-   Identifying a problem to solve and a metric for measuring results  
  
-   Finding, cleaning, and preparing appropriate data  
  
-   Identifying the best features and engineering new features  
  
-   Building, evaluating, and tuning models  
  
-   Using models to generate predictions, recommendations, and other results  
  
 The modules in this section provide tools for the final phases of machine learning, in which you apply an algorithm to data to train a model, generate scores, and then evaluate the accuracy and usefulness of the model.  
  
-   [Initialize Model](machine-learning-initialize-model.md): Choose from a variety of customizable machine learning algorithms, including [clustering](machine-learning-initialize-model-clustering.md), [regression](machine-learning-evaluate.md), [classification](machine-learning-evaluate.md), and  [anomaly detection](anomaly-detection.md) models.  
  
-   [Train](machine-learning-train.md): Provide your data to the configured model to  learn from patterns and create statistics that can be used for predictions.  
  
-   [Score](machine-learning-score.md): Create predictions using the trained models.  
  
-   [Evaluate](machine-learning-evaluate.md): Measure the accuracy of a trained model or compare multiple models.  
  
> [!TIP]
>  For a detailed description of this experimental workflow, see the [credit risk solution walkthrough](http://azure.microsoft.com/documentation/articles/machine-learning-walkthrough-develop-predictive-solution/).  
  
##  <a name="categories"></a> Categories  
 Click the links in the table to see a complete list of the Machine Learning modules in each category:  
  
|Category|  
|--------------|  
|[Machine Learning / Evaluate](machine-learning-evaluate.md)|  
|[Machine Learning / Initialize Model](machine-learning-initialize-model.md)|  
|[Machine Learning / Score](machine-learning-score.md)|  
|[Machine Learning / Train](machine-learning-train.md)|  
  
## Related Resources  
 For examples of machine learning in action, see the [Model Gallery](http://azure.microsoft.com/documentation/services/machine-learning/models/).  
  
 **Data Exploration and Data Quality**  
  
 Part of the machine learning process is making sure your data is the right kind of data, the right quantity, and the right quality for the algorithm you’ve chosen. Understand how much data you have, how it is distributed. Are there outliers? How were those generated and what do they mean? Are there any duplicate records?  
  
 For examples, see [Advanced data processing in Azure](http://azure.microsoft.com/documentation/articles/machine-learning-data-science-advanced-data-processing/).  
  
 **Missing Value Handling**  
  
 Missing values can affect your results in many ways. For example, almost all statistical methods discard cases with missing values. If you want to impute the missing values or correct your data, use [Clean Missing Data](clean-missing-data.md) before training your model.  
  
 By default, Azure Machine Learning follows these rules when it encounters rows with missing values:  
  
-   If data used to train a model has missing values, any rows with missing values are skipped.  
  
-   If data used as input when scoring against a model has missing values, the missing values are used as inputs, but nulls are propagated, which usually means that the result is also a missing value.  
  
 **Feature Selection and Dimensionality Reduction**  
  
 Azure Machine Learning Studio can help you sift through your data to find the most useful attributes.  
  
-   Use tools such as [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) or [Filter Based Feature Selection](filter-based-feature-selection.md) to determine which columns of data have the most predictive power, or to identify columns that should be removed because of *data leakage*.  
  
-   Create or engineer features from existing data. [Normalize Data](normalize-data.md) or [Group Data into Bins](group-data-into-bins.md) to make new groupings of data or standardize the range of numeric values prior to analysis.  
  
-   Reduce dimensionality by [grouping categorical values](group-categorical-values.md), by using [Principal Component Analysis](principal-component-analysis.md), or by [sampling](partition-and-sample.md).  
  
 **Choosing an Algorithm**  
  
 The problem you are trying to solve determines both the choice of data to use in analysis, and the choice of an algorithm.  
  
 For help in choosing a machine learning algorithm, see [How to choose an algorithm in Azure Machine Learning](http://azure.microsoft.com/documentation/articles/machine-learning-algorithm-choice/).  
  
## See Also  
 [Data Transformation](data-transformation.md)   
 [Data Input and Output](data-input-and-output.md)   
 [Statistical Functions](statistical-functions.md)