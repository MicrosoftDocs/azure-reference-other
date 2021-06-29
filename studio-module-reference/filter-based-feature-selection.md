---
title: "ML Studio (classic): Filter Based Feature Selection - Azure"
description: Learn how to use the Filter Based Feature Selection module to identify the columns in your input dataset that have the greatest predictive power.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Filter Based Feature Selection
*Identifies the features in a dataset with the greatest predictive power*  
  
 Category: [Feature Selection Modules](feature-selection-modules.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
##  Module overview  

This article describes how to use the [Filter Based Feature Selection](filter-based-feature-selection.md) module in Machine Learning Studio (classic), to identify the columns in your input dataset that have the greatest predictive power. 

In general, *feature selection* refers to the process of applying statistical tests to inputs, given a specified output, to determine which columns are more predictive of the output. The [Filter Based Feature Selection](filter-based-feature-selection.md) module provides multiple feature selection algorithms to choose from, including correlation methods such as Pearsons's or Kendall's correlation, mutual information scores, and chi-squared values. Machine Learning also supports feature value counts as an indicator of information value.
 
When you use the [Filter Based Feature Selection](filter-based-feature-selection.md) module, you provide a dataset, identify the column that contains the label or dependent variable, and then specify a single method to use in measuring feature importance.

The module outputs a dataset that contains the best feature columns, as ranked by predictive power. It also outputs the names of the features and their scores from the selected metric.  

### What is filter-based feature selection and why use it?  

This module for feature selection is called "filter-based" because you use the selected metric to identify irrelevant attributes, and filter out redundant columns from your model.  You choose a single statistical measure that suits your data, and the module calculates a score for each feature column. The columns are returned ranked by their feature scores. 

By choosing the right features, you can potentially improve the accuracy and efficiency of classification. 

You typically use only the columns with the best scores to build your predictive model. Columns with poor feature selection scores can be left in the dataset and ignored when you build a model.  
  
### How to choose a feature selection metric

The **Filter-Based Feature Selection** provides a variety of metrics for assessing the information value in each column.  This section provides a general description of each metric, and how it is applied. Additional requirements for using each metric are stated in the [Technical Notes](#bkmk_Notes) section and in the [instructions](#Configuration) for configuring each module.
  
-   **Pearson Correlation**  
  
     Pearson’s correlation statistic, or Pearson’s correlation coefficient, is also known in statistical models as the `r` value. For any two variables, it returns a value that indicates the strength of the correlation
  
     Pearson's correlation coefficient is computed by taking the covariance of two variables and dividing by the product of their standard deviations. The coefficient is not affected by changes of scale in the two variables.  
  
-   **Mutual Information**  
  
     The mutual information score measures the contribution of a variable towards reducing uncertainty about the value of another variable: namely, the label. Many variations of the mutual information score have been devised to suit different distributions.  
  
     The mutual information score is particularly useful in feature selection because it maximizes the mutual information between the joint distribution and target variables in datasets with many dimensions.  
  
-   **Kendall Correlation**  
  
     Kendall's rank correlation is one of several statistics that measure the relationship between rankings of different ordinal variables or different rankings of the same variable. In other words, it measures the similarity of orderings when ranked by the quantities. Both this coefficient and Spearman’s correlation coefficient are designed for use with non-parametric and non-normally distributed data.
  
-   **Spearman Correlation**  
  
     Spearman's coefficient is a nonparametric measure of statistical dependence between two variables, and is sometimes denoted by the Greek letter rho. The Spearman’s coefficient expresses the degree to which two variables are monotonically related. It is also called Spearman rank correlation, because it can be used with ordinal variables.  
  
-   **Chi Squared**  
  
     The two-way chi-squared test is a statistical method that measures how close expected values are to actual results. The method assumes that variables are random and drawn from an adequate sample of independent variables. The resulting chi-squared statistic indicates how far results are from the expected (random) result.  
  
-   **Fisher Score**  
  
     The Fisher score (also called the Fisher method, or Fisher combined probability score) is sometimes termed the information score, because it represents the amount of information that one variable provides about some unknown parameter on which it depends.  
  
     The score is computed by measuring the variance between the expected value of the information and the observed value. When variance is minimized, information is maximized. Since the expectation of the score is zero, the Fisher information is also the variance of the score.
  
-   **Count Based**  
  
     Count-based feature selection is a simple yet relatively powerful way of finding information about predictors. The basic idea underlying count-based featurization is simple: by calculating counts of individual values within a column, you can get an idea of the distribution and weight of values, and from this, understand which columns contain the most important information. 
     
     Count-based feature selection is a non-supervised method of feature selection, meaning you don't need a label column. This method also reduces the dimensionality of the data without losing information.    
  
     For more information about how count-based features are created and why they are useful in machine learning, see  [Learning with Counts](data-transformation-learning-with-counts.md).  
  
> [!TIP]
> If you need a different option for custom feature selection method, use the [Execute R Script](execute-r-script.md) module. 

##  <a name="Configuration"></a> How to configure Filter-Based Feature Selection

This module provides two methods for determining feature scores: 

 + [Generate feature scores using a traditional statistical metric](#bkmk_correlationMethods)
 
    You choose a standard statistical metric, and the module computes the correlation between a pair of columns, the label column and a feature column
 
+ [Use count-based feature selection](#bkmk_countMethod)

    With the count-based method, the module calculates a score based purely on the values in the column.
    
### <a name="bkmk_correlationMethods"></a> Generate feature scores using a traditional statistical metric
 
1.  Add the **Filter-Based Feature Selection** module to your experiment. You can find it in the **Feature Selection** category in Studio (classic).

2. Connect an input dataset that contains at least two columns that are potential features.  

    To ensure that a column should be analyzed and a feature score generated, use the [Edit Metadata](edit-metadata.md) module to set the **IsFeature** attribute. 

    > [!IMPORTANT]
    > Ensure that the columns you are providing as input are potential features. For example, a column that contains a single value has no information value.
    > 
    > If you know there are columns that would make bad features, you can remove them from the column selection. You could also use the [Edit Metadata](edit-metadata.md) module to flag them as **Categorical**. 
     
3.  For **Feature scoring method**, choose one of the following established statistical methods to use in calculating scores.  
  
    | Method| Requirements|
    |----|----|
    |Pearson Correlation|Label can be text or numeric. Features must be numeric. | 
    |Mutual Information| Labels and features can be text or numeric. Use this method for computing feature importance for two categorical columns.|
    |Kendall Correlation| Label can be text or numeric but features must be numeric.|
    |Spearman Correlation | Label can be text or numeric but features must be numeric.|
    Chi Squared| Labels and features can be text or numeric. Use this method for computing feature importance for two categorical columns.|
    |Fisher Score | Label can be text or numeric but features must be numeric.|
    |Counts| See: [To use Count-Based Feature Selection](#bkmk_countMethod)  
  
    > [!TIP]
    > If you change the selected metric, all other selections will be reset, so be sure to set this option first!)
     
  
4.  Select the **Operate on feature columns only** option to generate a score only for those columns that have been previously marked as features. 

    If you deselect this option, the module will create a score for any column that otherwise meets the criteria, up to the number of columns specified in **Number of desired features**.  
  
5.  For **Target column**, click **Launch column selector** to choose the label column either by name or by its index (indexes are one-based).  
  
     A label column is required for all methods that involve statistical correlation. The module returns a design-time error if you choose no label column or multiple label columns. 
  
6.  For **Number of desired features**, type the number of feature columns you want returned as a result.  
  
     - The minimum number of features you can specify is 1, but we recommend that you increase this value.  
  
     - If the specified number of desired features is greater than the number of columns in the dataset, then all features are returned, even those with zero scores.  
     
    - If you specify fewer result columns than there are feature columns, the features are ranked by descending score, and only the top features are returned. 
  
7.  Run the experiment, or select the [Filter Based Feature Selection](filter-based-feature-selection.md) module and then click **Run selected**.
  
### Results of feature selection

After processing is complete:

+ To see a complete list of the feature columns that were analyzed, and their scores, right-click the module, select **Features**, and click **Visualize**.  
  
+ To view the dataset that is generated based on your feature selection criteria, right-click the module, select **Dataset**, and click **Visualize**. 

If the dataset contains fewer columns than you expected, check the module settings, and the data types of the columns provided as input. For example, if you set **Number of desired features** to 1, the output dataset contains just two columns: the label column, and the most highly ranked feature column.

###  <a name="bkmk_countMethod"></a> Use count-based feature selection  
  
1.  Add the **Filter-Based Feature Selection** module to your experiment. You can find it in the list of modules in Studio (classic), in the **Feature Selection** group.

2. Connect an input dataset that contains at least two columns that are possible features.  
  
3.  Select **Count Based** from the list of statistical methods in the **Feature scoring method** dropdown list.  
4.  For **Minimum number of non-zero elements**, indicate the minimum number of feature columns to include in the output. 

    By default, the module outputs all columns that meet the requirements. The module cannot output any column that gets a score of zero.
  
5.  Run the experiment, or select just the module, and click **Run Selected**.

### Results of count-based feature selection

+ To see the list of feature columns with their scores, right-click the module, select **Features**, and click **Visualize** . 
+ To see the dataset containing the analyzed columns, right-click the module, select **Dataset**, and click **Visualize**.    
    
Unlike other methods, the **Count Based** feature selection method does not rank the variables by highest scores, but returns all variables with a non-zero score, in their original order.  
    
String features always get a zero (0) score and are thus are not output.

## Examples  

You can see examples of how feature selection is used in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
-   [Text Classification](https://gallery.azure.ai/Experiment/cf65bf129fee4190b6f48a53e599a755); In the third step of this sample, **Filter-Based Feature Selection** is used to identify the 15 best features. Feature hashing is used to convert the text documents to numeric vectors. Pearson’s correlation is then used on the vector features.
  
-  [Machine learning feature selection and feature engineering](https://azure.microsoft.com/documentation/articles/machine-learning-feature-selection-and-engineering/): This article provides an introduction to feature selection and feature engineering in machine learning.

To see examples of feature scores, see [Table of scores compared](#bkmk_ScoreExamples).

##  <a name="bkmk_Notes"></a> Technical notes  

You can find this module under **Data Transformation**, in the **Filters** category. 

### Implementation details

If you use Pearson Correlation, Kendall Correlation, or Spearman Correlation on a numeric feature and a categorical label, the feature score is calculated as follows:  
  
1.  For each level in the categorical column, compute the conditional mean of numeric column.  
  
2.  Correlate the column of conditional means with the numeric column.  
  
### Requirements  
  
-   A feature selection score cannot be generated for any column that is designated as a **label** or as a **score** column.  
  
-   If you attempt to use a scoring method with a column of a data type not supported by the method, either the module will raise an error, or a zero score will be assigned to the column.  
  
-   If a column contains logical (true/false) values, they are processed as True = 1 and False = 0.  
  
-   A column cannot be a feature if it has been designated as a **Label** or a **Score**.  
  
### How missing values are handled  
  
-   You cannot specify as a target (label) column any column that has all missing values.  
  
-   If a column contains missing values, they are ignored when computing the score for the column.  
  
-   If a column designated as a feature column has all missing values, a zero score is assigned.  

### <a name="bkmk_ScoreExamples"></a> Table of scores compared

To give you an idea of how the scores compare when using different metrics, the following table presents some feature selection scores from multiple features in the automobile price dataset, given the dependent variable **highway-mpg**.


|Feature column| Pearson score|Count score| Kendall score|Mutual information|
|-------|-------|-------|-------|-------|
|highway-mpg|1|205|1|1|
|city-mpg|0.971337|205|0.892472|0.640386|
|curb-weight|0.797465 |171|0.673447|0.326247|
|horsepower|0.770908|203|0.728289|0.448222|
|price|0.704692|201|0.651805|0.321788|
|length|0.704662205|205|0.53193|0.281317|
|engine-size|0.67747|205|0.581816|0.342399|
|width|0.677218|205|0.525585|0.285006|
|bore|0.594572|201|0.467345|0.263846|
|wheel-base|0.544082|205|0.407696|0.250641|
|compression-ratio|0.265201|205|0.337031 |0.288459|
|fuel-system|na|na|na|0.308135|
|make|na|na|na|0.213872|
|drive-wheels|na|na|na|0.213171|
|height|na|na|na|0.1924|
|normalized-losses|na|na|na|0.181734|
|symboling|na|na|na|0.159521|
|num-of-cylinders|na|na|na|0.154731|
|engine-type|na|na|na|0.135641|
|aspiration|na|na|na|0.068217|
|body-style|na|na|na|0.06369|
|fuel-type|na|na|na|0.049971
|num-of-doors|na|na|na|0.017459 |
|engine-location|na|na|na|0.010166 |


+ Mutual information scores can be created for all column types, including strings.

+ The other scores included in this table, such as Pearson's correlation or count-based feature selection, require numeric values. String features get a score of 0 and hence are not included in the output. For exceptions, see the [Technical Notes](#bkmk_Notes) section.

+ The count-based method does not treat a label column any differently from feature columns.    

##  Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Feature scoring method|List|Scoring method||Choose the method to use for scoring|  
|Operate on feature columns only|Any|Boolean|true|Indicate whether to use only feature columns in the scoring process|  
|Target column|Any|ColumnSelection|None|Specify the target column|  
|Number of desired features|>=1|Integer|1|Specify the number of features to output in results|  
|Minimum number of non-zero elements|>=1|Integer|1|Specify the number of features to output (for CountBased method)|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filtered dataset|[Data Table](data-table.md)|Filtered dataset|  
|Features|[Data Table](data-table.md)|Names of output columns and feature selection scores|  
  
##  Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0004](errors/error-0004.md)|Exception occurs if parameter is less than or equal to specific value.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).

## See also  
 [Feature Selection](feature-selection-modules.md)   
 [Fisher Linear Discriminant Analysis](fisher-linear-discriminant-analysis.md)   
 [A-Z Module List](a-z-module-list.md)
