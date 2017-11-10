---
title: "Feature Selection Modules | Microsoft Docs"
ms.custom: ""
ms.date: 05/31/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cc98f178-b2ed-44a0-8b35-8d02b266f20b
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Feature Selection Modules
This section describes the modules that are provided in Azure Machine Learning for performing feature selection.  Each module takes a dataset as input, and applies well-known statistical methods to the data columns provided as input. The output is generally a set of metrics that you can use to identify the columns that have the best information value. Multiple feature selection modules are provided; you should choose one depending on the type of data that you have, and the requirements of the statistical technique that is applied.

+ [What is feature selection](#bkmk_Introduction)
+ [Feature selection modules in Azure Machine Learning](#bkmk_ModulesDescribed)
+ [How to use feature selection](#bkmk_howto)
+ [Algorithms that include feature selection](#LearnersWithFeatureSelection)
 
 ## <a name="bkmk_Introduction"></a> Introduction to Feature Selection
 
 In machine learning and statistics, *feature selection* is the process of selecting a subset of relevant, useful features for use in building an analytical model. Feature selection helps narrow the field of data to just the most valuable inputs, reducing noise and improving training performance.  
  
 Often features are created from the raw data through a process of feature engineering. For example, a time stamp in itself might not be useful for modelling until transformed into units of days, months, or categories relevant to the problem such as holiday vs. working day, etc.  
  
 New users of machine learning are often tempted to add in all data that is available, expecting the algorithm will find something interesting. However, feature selection can improve your model and prevent problems.  
  
-   The data might contain redundant or irrelevant features, which provide no more information than the currently selected features.  
  
-   The data might also contain irrelevant features that provide no useful information in any context.  
  
-   Including irrelevant fields not only increases the time for training the data, but also can lead to poor results.  
  
-   With some algorithms, having duplicate information in the training data can lead to a phenomenon called multicollinearity, in which the presence of two highly correlated variables can cause the calculations for other variables to become much less accurate.  
  
 Machine Learning Studio provides multiple feature selection methods so that you can work with all data types. Additionally, some machine learning algorithms use some kind of feature selection or dimensionality reduction as part of the learning process. When you use these learners, you can skip the feature selection process and let the algorithm decide the best inputs.  
  
 These options are summarized here to help you choose the method most suited to your problem and to your data.  
  
##  <a name="bkmk_ModulesDescribed"></a> Feature Selection in Azure Machine Learning  

The following feature selection modules are provided in Azure Machine Learning Studio.  

### Filter-Based Feature Selection

The [Filter-Based Feature Selection](filter-based-feature-selection.md) module lets you choose from among well-known feature selection methods, and outputs both the feature selection statistics, and the filtered dataset.  
  
 Your choice of a filter selection method depends in part on what sort of input data you have.  
  
|Method|Supported Feature Inputs|Supported Labels|  
|------------|------------------------------|----------------------|  
|Pearson's correlation|Numeric and logical columns only|A single numeric or logical column|  
|Mutual information score|All data types|A single column of any data type|  
|Kendall's correlation coefficient|Numeric and logical columns only|A single numeric or logical column. Columns should have values that can be ranked.|  
|Spearman's correlation coefficient|Numeric and logical columns only|A single numeric or logical column|  
|Chi-squared statistic|All data types|A single column of any data type|  
|Fisher score|Numeric and logical columns only|A single numeric or logical column. String columns are assigned a score of 0.|  
|Count based feature selection|All data types|A label column is not required|  

### Fisher Linear Discriminant Analysis
  
Linear Discriminant Analysis is a supervised learning technique that can be used for classifying numerical variables in conjunction with a single categorical target. The method is useful for feature selection because it identifies the combination of features or parameters that best separates the groups.  
  
You can use the [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) module just to generate a set of scores for review, or you can use the replacement dataset generated by the module for training.  
 
### Permutation Feature Importance

[Permutation Feature Importance](permutation-feature-importance.md) lets you simulate the effect of any set of features on your dataset, by computing performance scores for a model based on random shuffling of feature values.

The scores that the module returns represent the potential change in the accuracy of a trained model if values change. You can use the scores to determine the effect of individual variables on the model.


### Related Tasks

Although the following modules are not included in the Feature Selection group, they can be useful in reducing the dimensionality of your data, or for finding correlations.
  
+ [Principal Component Analysis](principal-component-analysis.md)

  When you have a dataset with many columns, you can use the [Principal Component Analysis](principal-component-analysis.md) module to detect the columns that are the most useful; that is, the columns that contain the most information (variation) about the original data.  
  
  This module can be found in the the [Data Transformation](data-transformation.md) group, under [Scale and Reduce](data-transformation-scale-and-reduce.md).

+ [Learning with Counts](data-transformation-learning-with-counts.md)

   Count-based featurization is a new technique for determining useful features from large datasets. Using these modules, you can analyze datasets to find the best features, save a set of features to use with new data, or update an existing feature set.
 
+ [Compute Linear Correlation](compute-linear-correlation.md)

  Use this module to compute a set of Pearson correlation coefficients for each possible pair of variables in the input dataset. The Pearson correlation coefficient is also called Pearson’s R test, is a statistical value that measures the linear relationship between two variables. 
  
  This module can be found in the [Statistical Functions](statistical-functions.md) group.
  
## <a name="bkmk_howto"></a> How to Apply Feature Selection

Feature selection is typically performed when exploring data and developing a new model. You add a feature selection module to your experiment and attach a dataset to generate scores that inform your decision of which columns to use, and if the values in the columns are valid. You might remove the feature selection tasks from the experiment when you operationalize a model, and only periodically check the data to be sure that features have not changed.

Note that *feature selection* is different from *feature engineering*, which aims to create new features out of existing data.

+ For a discussion of the different ways that you can engineer features or select the best features, as part of the data sciece process, see this article: [Feature engineering in data science](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-create-features)
+ For a walkthrough of feature selection in the data science process, see [Filtering Features from Your Data - Feature Selection](https://docs.microsoft.com/azure/machine-learning/machine-learning-data-science-select-features)

### <a name="LearnersWithFeatureSelection"></a> Machine Learning Methods that Use Feature Selection  

Some learners in Azure Machine Learning Studio also provide parameters that can be used to optimize feature selection when training. If you are using a method that has its own heuristic for choosing features, it is often better to rely on that heuristic rather than pre-selecting features.  
  
+ Boosted Decision Tree Classification Models; Boosted Decision Tree Regression Models  

  In these modules, internally a feature summary is created and features with weight 0 are not used by any tree splits.  
  
  When you visualize the best trained model you can look at each of the trees. If a feature is never used in any tree then it is likely a candidate a for removal.
  
  Parameter sweeping is also recommended to optimize selection.  
  
+ Logistic Regression Models; Linear Classification Models  

  The modules for multiclass and binary logistic regression support L1 and L2 regularization.  

   Regularization is a way of adding constraints when training to manually specify some aspect of the learned model. Regularization is generally used to avoid overfitting. Machine Learning Studio supports regularization for the L1 or L2 norms of the weight vector in linear classification algorithms.  
  
  -   L1 regularization is useful if the goal is to have a model that is as sparse as possible.  
  
  -   L2 regularization prevents any single coordinate in the weight vector from growing too much in magnitude, so it is useful if the goal is to have a model with small overall weights.  
  
  -   L1-regularized logistic regression is more aggressive about assigning a weight of 0 to features, and therefore useful in identifying features that can be removed.  

## Technical Notes

All feature selection modules and analytical methods that support numeric and logical columns support date-time and time span columns as well. These columns are treated as simple numeric columns where each value equals to the number of ticks.  
  
##  <a name="modules"></a> List of Modules  
 
The Feature Selection category includes these modules:  
  
|Module|Description|  
|------------|-----------------|  
|[Filter Based Feature Selection](filter-based-feature-selection.md)|Identifies the features in a dataset with the greatest predictive power|  
|[Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)|Identifies the linear combination of feature variables that can best group data into separate classes|  
|[Permutation Feature Importance](permutation-feature-importance.md)|Computes the permutation feature importance scores of feature variables given a trained model and a test dataset|  


   
## See Also  
   
[Module Categories and Descriptions](machine-learning-module-descriptions.md)