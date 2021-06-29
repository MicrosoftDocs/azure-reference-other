---
title: "ML Studio (classic): Two-Class Logistic Regression - Azure"
description: Learn how to use the Two-Class Logistic Regression module to create a logistic regression model to predict a target that has only two values.
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Two-Class Logistic Regression
*Creates a two-class logistic regression model*  
  
 Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md) 

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)] 
  
##  Module overview  

This article describes how to use the **Two-Class Logistic Regression** module in Machine Learning Studio (classic), to create a logistic regression model that can be used to predict two (and only two) outcomes. 

Logistic regression is a well-known statistical technique that is used for modeling many kinds of problems. This algorithm is a *supervised learning* method;  therefore, you must provide a dataset that already contains the outcomes to train the model.  

### More about logistic regression  

Logistic regression is a well-known method in statistics that is used to predict the probability of an outcome, and is especially popular for classification tasks. The algorithm predicts the probability of occurrence of an event by fitting data to a logistic function. For details about this implementation, see the [Technical Notes](#bkmk_Notes) section.  
  
In this module, the classification algorithm is optimized for dichotomous or binary variables. if you need to classify multiple outcomes, use the [Multiclass Logistic Regression](multiclass-logistic-regression.md) module.

##  How to configure Two-Class Logistic Regression  

To train this model, you must provide a dataset that contains a label or class column. Because this module is intended for two-class problems, the label or class column must contain exactly two values. 

For example, the label column might be [Voted] with possible values of "Yes" or "No". Or, it might be [Credit Risk], with possible values of "High" or "Low". 
  
1.  Add the **Two-Class Logistic Regression** module to your experiment in Studio (classic).  
  
2.  Specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**: If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**: If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  The trainer iterates over multiple combinations of the settings and determines the combination of values that produces the best model.  
  
3.  For **Optimization tolerance**, specify a threshold value to use when optimizing the model. If the improvement between iterations falls below the specified threshold, the algorithm is considered to have converged on a solution, and training stops.  
  
4.  For **L1 regularization weight** and **L2 regularization weight**, type a value to use for the regularization parameters L1 and L2. A non-zero value is recommended for both.  
  
     *Regularization* is a method for preventing overfitting by penalizing models with extreme coefficient values. Regularization works by adding the penalty that is associated with coefficient values to the error of the hypothesis. Thus, an accurate model with extreme coefficient values would be penalized more, but a less accurate model with more conservative values would be penalized less.  
  
     L1 and L2 regularization have different effects and uses.  
  
    -   L1 can be applied to sparse models, which is useful when working with high-dimensional data.  
  
    -   In contrast, L2 regularization is preferable for data that is not sparse.  
  
     This algorithm supports a linear combination of L1 and L2 regularization values: that is, if <code>x = L1</code> and <code>y = L2</code>, then <code>ax + by = c</code> defines the linear span of the regularization terms.  
  
    > [!NOTE]
    >  Want to learn more about L1 and L2 regularization? The following article provides a discussion of how L1 and L2 regularization are different and how they affect model fitting, with code samples for logistic regression and neural network models:  [L1 and L2 Regularization for Machine Learning](https://msdn.microsoft.com/magazine/dn904675.aspx)  
    >
    > Different linear combinations of L1 and L2 terms have been devised for logistic regression models: for example, [elastic net regularization](https://wikipedia.org/wiki/Elastic_net_regularization). We suggest that you reference these combinations to define a linear combination that is effective in your model.
      
5.  For **Memory size for L-BFGS**, specify the amount of memory to use for *L-BFGS* optimization.  
  
     L-BFGS stands for "limited memory Broyden-Fletcher-Goldfarb-Shanno". It is an optimization algorithm that is popular for parameter estimation. This parameter indicates the number of past positions and gradients to store for the computation of the next step.  
  
     This optimization parameter limits the amount of memory that is used to compute the next step and direction. When you specify less memory, training is faster but less accurate.  
  
6.  For **Random number seed**, type an integer value. Defining a seed value is important if you want the results to be reproducible over multiple runs of the same experiment.  
  
7.  Select the **Allow unknown categorical levels** option to create an additional “unknown” level in each categorical column. If you do so, any values (levels) in the test dataset that are not available in the training dataset are mapped to this "unknown" level.
  
8. Add a tagged dataset to the experiment, and connect one of the [training modules](machine-learning-train.md).  
  
    -   If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  
  
    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  
  
9. Run the experiment.  
  
### Results

After training is complete:

+ To see a summary of the model's parameters, together with the feature weights learned from training, right-click the output of [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md), and select **Visualize**.   
  
+ To make predictions on new data, use the trained model and new data as input to the [Score Model](score-model.md) module. 

+ To perform cross-validation against a labeled data set, connect the data and the untrained model to [Cross-Validate Model](cross-validate-model.md).  
  
## Examples

For examples of how this learning algorithm is used, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [Network intrusion detection](https://go.microsoft.com/fwlink/?LinkId=525724): Uses binary logistic regression to determine whether a case represents an intrusion.  

- [Cross-Validation for Binary Classifier](https://go.microsoft.com/fwlink/?LinkId=525735): Demonstrates the use of logistic regression in a typical experimental workflow, including model evaluation.  

##  <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

Logistic regression requires numeric variables. Therefore, when you use categorical columns as variable, Machine Learning converts the values to an indicator array internally.

For dates and times, a numeric representation is used. (For more information about date time values, see [DateTime Structure (.NET Framework) - Remarks](https://msdn.microsoft.com/library/system.datetime\(v=vs.110\).aspx).) If you want to handle dates and times differently we suggest that you create a derived column.  

### Implementation details

Logistic regression assumes a *logistic distribution* of the data, where the probability that an example belongs to class 1 is the formula:  
  
 <code>p(x;β0,…, βD-1)</code>  
  
 Where:  
  
-   <code>x</code> is a D-dimensional vector containing the values of all the features of the instance.  
  
-   <code>p</code> is the logistic distribution function.  
  
-   <code>β{0},..., β {D-1}</code> are the unknown parameters of the logistic distribution.  
  
The algorithm tries to find the optimal values for <code>β{0},..., β {D-1}</code> by maximizing the log probability of the parameters given the inputs. Maximization is performed by using a popular method for parameter estimation, called [Limited Memory BFGS](https://en.wikipedia.org/wiki/Limited-memory_BFGS).  

### Research

For more information on the implementation of this algorithm, see [Scalable Training of L-1 Regularized Log-Linear Models](https://research.microsoft.com/apps/pubs/default.aspx?id=78900), by Andrew and Gao.  

##  Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Optimization tolerance|>=double.Epsilon|Float|0.0000001|Specify a tolerance value for the L-BFGS optimizer|  
|L1 regularization weight|>=0.0|Float|1.0|Specify the L1 regularization weight|  
|L2 regularization weight|>=0.0|Float|1.0|Specify the L2 regularization weight|  
|Memory size for L-BFGS|>=1|Integer|20|Specify the amount of memory (in MB) to use for the L-BFGS optimizer|  
|Random number seed|Any|Integer||Type a value to seed the random number generator used by the model. Leave it blank for the default.|  
|Allow unknown categorical levels|Any|Boolean|True|Indicate whether an additional level should be created for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained classification model|  
  
## See also  

[Classification](machine-learning-initialize-model-classification.md)   

[Multiclass Logistic Regression](multiclass-logistic-regression.md)   

[A-Z Module List](a-z-module-list.md)
