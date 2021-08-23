---
title: "ML Studio (classic): Feature Selection modules - Azure"
description: "Learn about the Machine Learning Studio (classic) modules that you can use for feature selection."
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Feature Selection modules

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

This article describes the modules in Machine Learning Studio (classic) that you can use for feature selection.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

Feature selection is an important tool in machine learning. Machine Learning Studio (classic) provides multiple methods for performing feature selection. Choose a feature selection method based on the type of data that you have, and the requirements of the statistical technique that's applied.

This article covers:

- [What is feature selection](#bkmk_Introduction)
- [Feature selection modules in Machine Learning](#bkmk_ModulesDescribed)
- [How to use feature selection](#bkmk_howto)
- [Algorithms that include feature selection](#LearnersWithFeatureSelection)

Each feature selection module in Machine Learning Studio (classic) uses a dataset as input. Then, the module applies well-known statistical methods to the data columns that are provided as input. The output is a set of metrics that can help you identify the columns that have the best information value.

## <a name="bkmk_Introduction"></a>About feature selection
 
In machine learning and statistics, *feature selection* is the process of selecting a subset of relevant, useful features to use in building an analytical model. Feature selection helps narrow the field of data to the most valuable inputs. Narrowing the field of data helps reduce noise and improve training performance.
 
Often, features are created from raw data through a process of feature engineering. For example, a time stamp in itself might not be useful for modeling until the information is transformed into units of days, months, or categories that are relevant to the problem, such as holiday versus working day.
 
New users of machine learning might be tempted to include all data that's available. They might expect that the algorithm will find something interesting by using more data. However, feature selection can usually improve your model, and prevent common problems:

- The data contains redundant or irrelevant features, which provide no more information than the currently selected features.
- The data contains irrelevant features that provide no useful information in any context. Including irrelevant fields not only increases the time required to train the data, but also can lead to poor results.
- With some algorithms, having duplicate information in the training data can lead to a phenomenon called *multicollinearity*. In multicollinearity, the presence of two highly correlated variables can cause the calculations for other variables to become much less accurate.
 
> [!TIP]
> 
> Some machine learning algorithms in Machine Learning Studio (classic) also use feature selection or dimensionality reduction as part of the training process. When you use these learners, you can skip the feature selection process and let the algorithm decide the best inputs.

### <a name="bkmk_howto"></a>Use feature selection in an experiment

Feature selection typically is performed when you are exploring data and developing a new model. Keep these tips in mind when you use feature selection:

- When testing, add feature selection to your experiment to generate scores that inform your decision of which columns to use.
- Remove feature selection from the experiment when you operationalize a model.
- Run feature selection periodically to ensure that the data and best features haven't changed.

Feature selection is different from feature engineering, which focuses on creating new features out of existing data.

### Resources

- For a discussion of the different ways that you can engineer features or select the best features as part of the data science process, see [Feature engineering in data science](/azure/machine-learning/machine-learning-data-science-create-features).
- For a walkthrough of feature selection in the data science process, see [Filter features from your data - Feature selection](/azure/machine-learning/machine-learning-data-science-select-features).

## <a name="bkmk_ModulesDescribed"></a>Feature selection methods in Machine Learning Studio (classic)

The following feature selection modules are provided in Machine Learning Studio (classic).

### Filter Based Feature Selection

When you use the [Filter Based Feature Selection](filter-based-feature-selection.md) module, you can choose from among well-known feature selection methods. The module outputs both the feature selection statistics and the filtered dataset.
 
Your choice of a filter selection method depends in part on what sort of input data you have.
 
|Method|Supported feature inputs|Supported labels|
|------------|------------------------------|----------------------|
|Pearson's correlation|Numeric and logical columns only|A single numeric or logical column|
|Mutual information score|All data types|A single column of any data type|
|Kendall's correlation coefficient|Numeric and logical columns only|A single numeric or logical column<br /><br />Columns should have values that can be ranked|
|Spearman's correlation coefficient|Numeric and logical columns only|A single numeric or logical column|
|Chi-squared statistic|All data types|A single column of any data type|
|Fisher score|Numeric and logical columns only|A single numeric or logical column<br /><br />String columns are assigned a score of 0|
|Count based feature selection|All data types|A label column is not required|

### Fisher Linear Discriminant Analysis
 
Linear Discriminant Analysis is a supervised learning technique that you can use to classify numerical variables in conjunction with a single categorical target. The method is useful for feature selection because it identifies the combination of features or parameters that best separates the groups.
 
You can use the [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md) module to generate a set of scores for review, or you can use the replacement dataset that's generated by the module for training.
 
### Permutation Feature Importance

Use the [Permutation Feature Importance](permutation-feature-importance.md) module to simulate the effect of any set of features on your dataset. The module computes performance scores for a model based on random shuffling of feature values.

The scores that the module returns represent the potential change in the accuracy of a trained model if values change. You can use the scores to determine the effect of individual variables on the model.

### <a name="LearnersWithFeatureSelection"></a>Machine learning algorithms that incorporate feature selection

Some machine learning algorithms in Machine Learning Studio (classic) optimize feature selection during training. They might also provide parameters that help with feature selection. If you're using a method that has its own heuristic for choosing features, it's often better to rely on that heuristic instead of preselecting features.

These algorithms and feature selection methods are used internally:

- **Boosted decision tree models for classification and regression**

  In these modules, a feature summary is created internally. Features that have a weight of 0 aren't used by any tree splits. When you visualize the best trained model, you can look at each of the trees. If a feature is never used in any tree, the feature is likely a candidate for removal. To optimize selection, it's also a good idea to use parameter sweeping.
 
- **Logistic regression models and linear models**

  The modules for multiclass and binary logistic regression support L1 and L2 regularization. Regularization is a way of adding constraints during training to manually specify an aspect of the learned model. Regularization typically is used to avoid overfitting. Machine Learning Studio (classic) supports regularization for the L1 or L2 norms of the weight vector in linear classification algorithms:
 
    - L1 regularization is useful if the goal is to have a model that's as sparse as possible.
    - L2 regularization prevents any single coordinate in the weight vector from growing too much in magnitude. It's useful if the goal is to have a model with small overall weights.
    - L1-regularized logistic regression is more aggressive about assigning a weight of 0 to features. It's useful in identifying features that can be removed.

## Technical notes

All feature selection modules and analytical methods that support numeric and logical columns also support date-time and timespan columns. These columns are treated as simple numeric columns in which each value equals the number of ticks.

## Related tasks

The following modules aren't in the **Feature Selection** category, but you can use them for related tasks. The modules can help you reduce the dimensionality of your data or find correlations:
 
- [Principal Component Analysis](principal-component-analysis.md)

 If you have a dataset that has many columns, use the [Principal Component Analysis](principal-component-analysis.md) module to detect the columns that contain the most information about the original data.
 
 This module is in the [Data Transformation](data-transformation.md) category, under [Scale and Reduce](data-transformation-scale-and-reduce.md).

- [Learning with Counts](data-transformation-learning-with-counts.md)

 Count-based featurization is a new technique that you can use to determine useful features by using large datasets. Use these modules to analyze datasets to find the best features, save a set of features to use with new data, or update an existing feature set.
 
- [Compute Linear Correlation](compute-linear-correlation.md)

 Use this module to compute a set of Pearson correlation coefficients for each possible pair of variables in the input dataset. The Pearson correlation coefficient, also called Pearson’s R test, is a statistical value that measures the linear relationship between two variables.
 
 This module is in the [Statistical Functions](statistical-functions.md) category.
 
## List of modules
 
The **Feature Selection** category includes these modules:
 
- [Filter Based Feature Selection](filter-based-feature-selection.md): Identifies the features in a dataset that have the greatest predictive power.
- [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md): Identifies the linear combination of feature variables that can best group data into separate classes.
- [Permutation Feature Importance](permutation-feature-importance.md): Computes the permutation feature importance scores of feature variables for a trained model and test dataset.

## See also
 
- [Module categories and descriptions](machine-learning-module-descriptions.md)
