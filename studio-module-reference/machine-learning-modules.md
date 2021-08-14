---
title: "ML Studio (classic): Machine Learning Modules - Azure"
description: The modules in this section provide tools for the final phases of machine learning.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Machine learning modules in ML Studio (classic) modules

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

The typical workflow for machine learning includes many phases:  
  
-   Identifying a problem to solve and a metric for measuring results.  
  
-   Finding, cleaning, and preparing appropriate data.  
  
-   Identifying the best features and engineering new features.  
  
-   Building, evaluating, and tuning models.  
  
-   Using models to generate predictions, recommendations, and other results.  
  
The modules in this section provide tools for the final phases of machine learning, in which you apply an algorithm to data to train a model. In these final phases, you also generate scores, and then evaluate the accuracy and usefulness of the model.  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## List of machine learning tasks by category

-   [Initialize Model](machine-learning-initialize-model.md)

    Choose from a variety of customizable machine learning algorithms, including [clustering](machine-learning-initialize-model-clustering.md), [regression](machine-learning-evaluate.md), [classification](machine-learning-evaluate.md), and  [anomaly detection](anomaly-detection.md) models.  
  
-   [Train](machine-learning-train.md)

    Provide your data to the configured model to  learn from patterns and create statistics that can be used for predictions.  
  
-   [Score](machine-learning-score.md)

    Create predictions using the trained models.  
  
-   [Evaluate](machine-learning-evaluate.md)

    Measure the accuracy of a trained model, or compare multiple models.  

For a detailed description of this experimental workflow, see the [credit risk solution walkthrough](/azure/machine-learning/classic/tutorial-part1-credit-risk).  

## Prerequisites

Before you can get to the fun part of building a model, typically a lot of preparation is required. This section provides links to tools in Machine Learning Studio (classic) that can help you clean up your data, improve the quality of input, and prevent run-time errors.

### Data exploration and data quality

Ensure that your data is the right kind of data, the right quantity, and the right quality for the algorithm you’ve chosen. Understand how much data you have, and how it is distributed. Are there outliers? How were those generated, and what do they mean? Are there any duplicate records?  

### Handle missing values

Missing values can affect your results in many ways. For example, almost all statistical methods discard cases with missing values. By default, Machine Learning follows these rules when it encounters rows with missing values:

+ If data used to train a model has missing values, any rows with missing values are skipped.

+ If data used as input when scoring against a model has missing values, the missing values are used as inputs, but nulls are propagated. This usually means that a null is inserted in the results instead of a valid prediction.

Be sure to check your data before training your model. To impute the missing values or correct your data, use this module:

+ [Clean Missing Data](clean-missing-data.md) 

### Select features and reduce dimensionality

Machine Learning Studio (classic) can help you sift through your data to find the most useful attributes.  
  
-   Use tools such as [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) or [Filter Based Feature Selection](filter-based-feature-selection.md) to determine which columns of data have the most predictive power. These tools can also identify columns that should be removed because of data leakage.  
  
-   Create or engineer features from existing data. [Normalize data](normalize-data.md) or [group data into bins](group-data-into-bins.md) to make new groupings of data, or standardize the range of numeric values prior to analysis.  
  
-   Reduce dimensionality by [grouping categorical values](group-categorical-values.md), by using [principal component analysis](principal-component-analysis.md), or by [sampling](partition-and-sample.md).  
  

## Examples

For examples of machine learning in action, see the [Azure AI Gallery](https://azure.microsoft.com/documentation/services/machine-learning/models/).

For tips, and a walkthrough of some typical data prepration tasks, see [Walkthroughs executing the Team Data Science Process](/azure/machine-learning/team-data-science-process/walkthroughs).


## See also  
- [Data Transformation](data-transformation.md)   
- [Data Input and Output](data-input-and-output.md)   
- [Statistical Functions](statistical-functions.md)
