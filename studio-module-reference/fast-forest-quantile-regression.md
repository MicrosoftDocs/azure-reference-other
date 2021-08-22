---
title: "ML Studio (classic): Fast Forest Quantile Regression - Azure"
description: Learn how to use the Fast Forest Quantile Regression module to create a regression model that can predict values for a specified number of quantiles.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Fast Forest Quantile Regression

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates a quantile regression model*  
  
 Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md) 

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)] 
  
## Module overview

This article describes how to use the **Fast Forest Quantile Regression** module in Machine Learning Studio (classic), to create a regression model that can predict values for a specified number of quantiles. 

Quantile regression is useful if you want to understand more about the distribution of the predicted value, rather than get a single mean prediction value. This method has many applications, including:  
  
-   Predicting prices  
  
-   Estimating student performance or applying growth charts to assess child development  
  
-   Discovering predictive relationships in cases where there is only a weak relationship between variables  
  
This regression algorithm is a **supervised** learning method, which means it requires a tagged dataset that includes a label column. Because it is a regression algorithm, the label column must contain only numerical values.

### More about quantile regression  

There are many different types of regression. In the most basic sense, regression means fitting a model to a target expressed as a numeric vector.  However, statisticians have been developing increasingly advanced methods for regression.

The simplest definition of *quantile* is a value that divides a set of data into equal-sized groups; thus, the quantile values mark the boundaries between groups. Statistically speaking, quantiles are values taken at regular intervals from the inverse of the cumulative distribution function (CDF) of a random variable.

Whereas linear regression models attempt to predict the value of a numeric variable using a single estimate, the *mean*, sometimes you need to predict the range or entire distribution of the target variable. Techniques such as Bayesian regression and quantile regression have been developed for this purpose. 

Quantile regression helps you understand the distribution of the predicted value.  Tree-based quantile regression models, such as the one used in this module, have the additional advantage that they can be used to predict non-parametric distributions.

For additional implementation details and resources, see the [Technical Notes](#bkmk_Notes) section.  
  
## How to configure Fast_Forest Quantile Regression 

You configure the properties of the regression model using this module, and then train it using one of the [training modules](machine-learning-train.md). 

Configuration steps differ considerably dependng on whether you are providing a fixed set of parameters, or setting up a parameter sweep.
  
-   [To create a quantile regression model using fixed parameters](#bkmk_FixedParameters)  
  
-   [To create a quantile regression model using a parameter sweep](#bkmk_ParameterSweep)  
  
###  <a name="bkmk_FixedParameters"></a> Create a quantile regression model using fixed parameters

Assuming you know how you want to configure the model, you can provide a specific set of values as arguments. When you train the model, use [Train Model](train-model.md).

1.  Add the **Fast Forest Quantile Regression** module to your experiment in Studio (classic).
  
2.  Set the **Create trainer mode** option to **Single Parameter**.  

3.  For **Number of Trees**, type the maximum number of trees that can be created in the ensemble. If you create more trees, it generally leads to greater accuracy, but at the cost of longer training time.  

4.  For **Number of Leaves**, type the maximum number of leaves, or terminal nodes, that can be created in any tree.  
  
5.  For **Minimum number of training instances required to form a leaf** , specify  the minimum number of examples that are required to create any terminal node (leaf) in a tree.  
  
     By increasing this value, you increase the threshold for creating new rules. For example, with the default value of 1, even a single case can cause a new rule to be created. If you increase the value to 5, the training data would have to contain at least 5 cases that meet the same conditions
  
6.  For **Bagging fraction**, specify a number between 0 and 1 that represents the fraction of samples to use when building each group of quantiles. Samples are chosen randomly, with replacement.
  
7.  For **Feature fraction**, type a number between 0 and 1 that indicates the fraction of total features to use when building any particular tree. Features are always chosen randomly.
  
8.  For **Split fraction**, type a number between 0 and 1 that represents the fraction of features to use in each split of the tree. The features used are always chosen randomly.
  
9. For **Quantile sample count**, type the number of cases to evaluate when estimating the quantiles.
  
10. For **Quantiles to be estimated**, type a comma-separated list of the quantiles for which you want the model to train and create predictions.
  
     For example, if you want to build a model that estimates for quartiles, you would type `0.25, 0.5, 0.75`.  
  
11. Optionally, type a value for **Random number seed** to seed the random number generator used by the model.  The default is 0, meaning a random seed is chosen.
  
     You should provide a value if you need to reproduce results across successive runs on the same data.  
  
12. Select the **Allow unknown categorical levels** option to create a group for unknown values.  
  
     If you deselect it, the model can accept only the values that are contained in the training data. 
     
     If you select this option, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.
  
13. Connect a training dataset, select a single label column, and connect  [Train Model](train-model.md).  
  
14. Run the experiment.  
  
###  <a name="bkmk_ParameterSweep"></a> Use a parameter sweep to create a quantile regression model

If you are not sure of the optimal parameters for the model, you can configure a parameter sweep, and provide a range of values as arguments. When you train the model, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.

1.  Add the **Fast Forest Quantile Regression** module to your experiment in Studio (classic).  
  
2.  Set the **Create trainer mode** option to **Parameter Range**.  
  
     A parameter sweep is recommended if you are not sure of the best parameters. By specifying multiple values and using the  [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to train the model, you can find the optimal set of parameters for your data.  
  
     After choosing a parameter sweep, for each property that is tunable, you can set either a single value, or multiple values. For example, you might decide to fix the number of trees, but randomly change other values that control the way each tree is built.
  
    -   If you type a single value, that value is used across all iterations of the sweep, even if other values change.
  
    -   Type a comma-separated list of discrete values to use. These values are used in combination with other properties. 
  
    -   Use the **Range Builder** to define a range of continuous values.  
  
     During the training process, the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module iterates over various combinations of the values to build the best model.  
  
3.  For **Maximum number of leaves per tree**, type the total number of leaves, or terminal nodes, to allow in each tree.  
  
4.  For **Number of trees constructed**, type the number of iterations to perform when constructing the ensemble. By creating more trees, you can potentially get better coverage, at the expense of increased training time.  
  
5.  For **Minimum number of sample per leaf node**, indicate how many cases are required to create a leaf node.  
  
     By increasing this value, you increase the threshold for creating new rules. For example, with the default value of 1, even a single case can cause a new rule to be created. If you increase the value to 5, the training data would have to contain at least 5 cases that meet the same conditions.  
  
6.  In **Range for bagging fraction**, type the fraction of samples to use when building each group of quantiles. Samples are chosen randomly, with replacement.
  
     Each fraction should be a number between 0 and 1. Separate multiple fractions, by using commas.
  
7.  In **Range for feature fraction**, type  the fraction of total features to use when building each group of quantiles. Features are chosen randomly.
  
     Each fraction should be a number between 0 and 1; separate multiple fractions by using commas.  
  
8.  In **Range for split fraction**, specify some fraction of features to use in each group of quantiles. The actual features used are chosen randomly.  
  
     Each fraction should be a number between 0 and 1; separate multiple fractions by using commas.  
  
9. In **Sample count used to estimate the quantiles**, indicate how many samples should be evaluated when estimating the quantiles. If you type a number greater than the number of available samples, all samples are used.
  
10. In **Required quantile values**, type a comma-separated list of the quantiles on which you want the model to train. For example, if you want to build a model that estimates quartiles, you would type `0.25, 0.5, 0.75
  
11. In **Random number seed**, type a value to seed the random number generator used by the model. Use of a seed is useful in order to reproduce duplicate runs.  
  
     The default is 0, meaning a random seed is chosen.  
  
12. Select the **Allow unknown values for categorical features** option to create a group for unknown values in the training or validation sets.  
  
     If you deselect this option, the model can accept only the values that are contained in the training data.
     
     If you select this option, the model might be less precise for known values, but it can provide better predictions for new (unknown) values.  
  
13. Connect a training dataset, select the label column, and connect the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  
  
    > [!NOTE]
    >  Do not use [Train Model](train-model.md). If you configure a parameter range but train using [Train Model](train-model.md), it uses only the first value in the parameter range list.  
  
14. Run the experiment.  
  
### Results

After training is complete:

+ To see the final hyperparameters of the optimized model, right-click the output of [Tune Model Hyperparameters](tune-model-hyperparameters.md) and select **Visualize**. 
## Examples

For examples of how to use this module, see the [Azure AI Gallery](https://gallery.azure.ai):  
  
- [Quantile Regression](https://go.microsoft.com/fwlink/?LinkId=525769): Demonstrates how to build and interpret a quantile regression model, using the auto price dataset.

##  <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

The **Fast Forest Quantile Regression** module in Machine Learning is an implementation of random forest quantile regression using decision trees. Random forests can be helpful to avoid overfitting that can occur with decision trees.  A decision tree is a binary tree-like flow chart, where at every interior node, one decides which of the two child nodes to continue to, based on the value of one of the features of the input.  
  
In each leaf node, a value is returned. In the interior nodes, the decision is based on the test ``x≤v`, where x is the value of the feature in the input sample and v is one of the possible values of this feature. The functions that can be produced by a regression tree are all the piece-wise constant functions.  
  
In a random forest, an ensemble of trees is created by using bagging to select a subset of random samples and features of the training data, and then fit a decision tree to each subset of data. Unlike the random forest algorithm, which averages out the output of the all the trees, **Fast Forest Quantile Regression** keeps all the predicted labels in trees specified by the parameter **Quantile sample count** and outputs the distribution, so that the user can view the quantile values for the given instance.

### Related research

For more information about quantile regression, see these books and articles:  
  
-   Quantile Regression Forests. Nicolai Meinshausen  
  
     [http://jmlr.org/papers/volume7/meinshausen06a/meinshausen06a.pdf](http://jmlr.org/papers/volume7/meinshausen06a/meinshausen06a.pdf)  
  
-   Random forests. Leo Breiman.  
  
     [https://rd.springer.com/article/10.1023%2FA%3A1010933404324](https://rd.springer.com/article/10.1023%2FA%3A1010933404324)  
  
##  Module parameters  

|Name|Type|Range|Optional|Description|Default|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Create trainer mode|CreateLearnerMode|List:Single Parameter&#124;Parameter Range|Required|Single Parameter|Create advanced learner options|  
|Number of Trees|Integer||mode:Single Parameter|100|Specify the number of trees to be constructed|  
|Number of Leaves|Integer||mode:Single Parameter|20|Specify the maximum number of leaves per tree. The default number is 20|  
|Minimum number of training instances required to form a leaf|Integer||mode:Single Parameter|10|Indicates the minimum number of training instances required to form a leaf|  
|Bagging fraction|Float||mode:Single Parameter|0.7|Specifies the fraction of training data to use for each tree|  
|Feature fraction|Float||mode:Single Parameter|0.7|Specifies the fraction of features (chosen randomly) to use for each tree|  
|Split fraction|Float||mode:Single Parameter|0.7|Specifies the fraction of features (chosen randomly) to use for each split|  
|Quantile sample count|Integer|Max: 2147483647|mode:Single Parameter|100|Specifies number of instances used in each node to estimate quantiles|  
|Quantiles to be estimated|String||mode:Single Parameter|"0.25;0.5;0.75"|Specifies the quantile to be estimated|  
|Random number seed|Integer||Optional||Provide a seed for the random number generator used by the model. Leave blank for default.|  
|Allow unknown categorical levels|Boolean||Required|true|If true, create an additional level for each categorical column. Levels in the test dataset not available in the training dataset are mapped to this additional level.|  
|Maximum number of leaves per tree|ParameterRangeSettings|[16;128]|mode:Parameter Range|16; 32; 64|Specify range for the maximum number of leaves allowed per tree|  
|Number of trees constructed|ParameterRangeSettings|[1;256]|mode:Parameter Range|16; 32; 64|Specify the range for the maximum number of trees that can be created during training|  
|Minimum number of samples per leaf node|ParameterRangeSettings|[1;10]|mode:Parameter Range|1; 5; 10|Specify the range for the minimum number of cases required to form a leaf|  
|Range for bagging fraction|ParameterRangeSettings|[0.25;1.0]|mode:Parameter Range|0.25; 0.5; 0.75|Specifies the range for fraction of training data to use for each tree|  
|Range for feature fraction|ParameterRangeSettings|[0.25;1.0]|mode:Parameter Range|0.25; 0.5; 0.75|Specifies the range for fraction of features (chosen randomly) to use for each tree|  
|Range for split fraction|ParameterRangeSettings|[0.25;1.0]|mode:Parameter Range|0.25; 0.5; 0.75|Specifies the range for fraction of features (chosen randomly) to use for each split|  
|Sample count used to estimate the quantiles|Integer||mode:Parameter Range|100|Sample count used to estimate the quantiles|  
|Required quantile values|String||mode:Parameter Range|"0.25;0.5;0.75"|Required quantile value used during parameter sweep|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained quantile regression model that can be connected to the Train Generic Model or Cross Validate Model modules.|  
  
## See also  
 [Regression](machine-learning-initialize-model-regression.md)
