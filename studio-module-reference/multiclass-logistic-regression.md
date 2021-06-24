---
title: "ML Studio (classic): Multiclass Logistic Regression - Azure"
description: Learn how to use the Multiclass Logistic Regression module to create a logistic regression model that can be used to predict multiple values.
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Multiclass Logistic Regression

*Creates a multiclass logistic regression classification model*

Category: [Machine Learning / Initialize Model / Classification](machine-learning-initialize-model-classification.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Multiclass Logistic Regression** module in Machine Learning Studio (classic), to create a logistic regression model that can be used to predict multiple values.

Classification using logistic regression is a supervised learning method, and therefore requires a labeled dataset. You train the model by providing the model and the labeled dataset as an input to a module such as [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md). The trained model can then be used to predict values for new input examples.

Machine Learning Studio (classic) also provides a [Two-Class Logistic Regression](two-class-logistic-regression.md) module, which is suited for classification of binary or dichotomous variables.

### More about multiclass logistic regression

Logistic regression is a well-known method in statistics that is used to predict the probability of an outcome, and is particularly popular for classification tasks. The algorithm predicts the probability of occurrence of an event by fitting data to a logistic function. For details about this implementation, see the [Technical Notes](#bkmk_Notes) section.

In multiclass logistic regression, the classifier can be used to predict multiple outcomes.

## How to configure a Multiclass Logistic Regression

1. Add the **Multiclass Logistic Regression** module to the experiment.

2. Specify how you want the model to be trained, by setting the **Create trainer mode** option.

    + **Single Parameter**: Use this option if you know how you want to configure the model, and provide a specific set of values as arguments.

    + **Parameter Range**: Use this option if you are not sure of the best parameters, and want to use a parameter sweep.

3. **Optimization tolerance**, specify the threshold value for optimizer convergence. If the improvement between iterations is less than the threshold, the algorithm stops and returns the current model.

4. **L1 regularization weight**, **L2 regularization weight**: Type a value to use for the regularization parameters L1 and L2. A non-zero value is recommended for both.

    Regularization is a method for preventing overfitting by penalizing models with extreme coefficient values. Regularization works by adding the penalty that is associated with coefficient values to the error of the hypothesis. An accurate model with extreme coefficient values would be penalized more, but a less accurate model with more conservative values would be penalized less.

     L1 and L2 regularization have different effects and uses. L1 can be applied to sparse models, which is useful when working with high-dimensional data. In contrast, L2 regularization is preferable for data that is not sparse.  This algorithm supports a linear combination of L1 and L2 regularization values: that is, if `x = L1` and `y = L2`, `ax + by = c` defines the linear span of the regularization terms.

     Different linear combinations of L1 and L2 terms have been devised for logistic regression models, such as [elastic net regularization](https://wikipedia.org/wiki/Elastic_net_regularization).

5. **Memory size for L-BFGS**: Specify the amount of memory to use for *L-BFGS* optimization. This parameter indicates the number of past positions and gradients to store for the computation of the next step.

    L-BFGS stands for limited memory Broyden-Fletcher-Goldfarb-Shanno, and it is an optimization algorithm that is popular for parameter estimation. This optimization parameter limits the amount of memory that is used to compute the next step and direction. When you specify less memory, training is faster but less accurate.

6. **Random number seed**: Type an integer value to use as the seed for the algorithm if you want the results to be repeatable over runs. Otherwise, a system clock value is used as the seed, which can produce slightly different results in runs of the same experiment.

7. **Allow unknown categorical levels**:   Select this option to create an additional “unknown” level in each categorical column. Any values (levels) in the test dataset that are not present in the training dataset are mapped to this "unknown" level.

8. Connect a labeled dataset, and one of the train modules:

    + If you set **Create trainer mode** to **Single Parameter**, use the [Train Model](train-model.md) module.

    + If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  With this option, you can specify multiple values, and the trainer iterates over multiple combinations of the settings to determine the combination of values that produces the best model.

    > [!NOTE]
    > 
    > If you pass a parameter range to [Train Model](train-model.md), it uses only the first value in the parameter range list.
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified is used throughout the sweep, even if other parameters change across a range of values.

9. Run the experiment.

### Results

After training is complete:

+ To see a summary of the model's parameters, together with the feature weights learned from training, right-click the output of the [Train Model](train-model.md) module or [Tune Model Hyperparameters](tune-model-hyperparameters.md), and select **Visualize**.

## Examples

For examples of how this learning algorithm is used, see the [Azure AI Gallery](https://gallery.azure.ai/):

+ [Iris clustering](https://gallery.azureml.net/Experiment/a7299de725a141388f373e9d74ef2f86): Compares the results of multiclass logistic regression with K-means clustering.

+ [Network intrusion detection](https://go.microsoft.com/fwlink/?LinkId=525724): Uses binary logistic regression to determine if a case represents an intrusion.

+ [Cross Validation for Binary Classifiers](https://go.microsoft.com/fwlink/?LinkId=525734): Demonstrates the use of logistic regression in a typical experimental workflow, including model evaluation.

## <a name="bkmk_Notes"></a> Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Related research

Want to learn more about L1 and L2 regularization? The following article provides a discussion of how L1 and L2 regularization are different and how they affect model fitting, with code samples for logistic regression and neural network models.  

+ [L1 and L2 Regularization for Machine Learning](https://msdn.microsoft.com/magazine/dn904675.aspx)

For more information on the implementation of this algorithm, see:

+ [Scalable Training of L-1 Regularized Log-Linear Models](https://research.microsoft.com/apps/pubs/default.aspx?id=78900), by Andrew and Gao.  

### Implementation details

Logistic regression requires numeric variables. Therefore, when you try to use categorical columns as a variable, Machine Learning converts the values to an indicator array internally.

For dates and times, a numeric representation is used. For more information about date time values, see [DateTime Structure .NET Framework](https://msdn.microsoft.com/library/system.datetime). If you want to handle dates and times differently we suggest that you create a derived column.  

Standard logistic regression is binomial and assumes two output classes. Multiclass or multinomial logistic regression assumes three or more output classes.

Binomial logistic regression assumes a *logistic distribution* of the data, where the probability that an example belongs to class 1 is the formula:

`p(x;β0,…, βD-1)`

 Where:

+ x is a D-dimensional vector containing the values of all the features of the instance.

+ p is the logistic distribution function.

+ `β{0},..., β {D-1}` are the unknown parameters of the logistic distribution.

The algorithm tries to find the optimal values for `β{0},..., β {D-1}` by maximizing the log probability of the parameters given the inputs. Maximization is performed by using a popular method for parameter estimation, called [Limited Memory BFGS](https://wikipedia.org/wiki/Limited-memory_BFGS).

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Optimization tolerance|>=double.Epsilon|Float|0.0000001|Specify a tolerance value for the L-BFGS optimizer|  
|L1 regularization weight|>=0.0|Float|1.0|Specify the L1 regularization weight. Use a non-zero value to avoid overfitting.|  
|L2 regularization weight|>=0.0|Float|1.0|Specify the L2 regularization weight. Use a non-zero value to avoid overfitting.|  
|Memory size for L-BFGS|>=1|Integer|20|Specify the amount of memory (in MB) to use for the L-BFGS optimizer. When less memory is used, training is faster, but less accurate.|  
|Random number seed|Any|Integer||Type a value to seed the random number generator used by the model. Leave it blank for the default.|  
|Allow unknown categorical levels|Any|Boolean|True|Indicate whether an additional level should be created for each categorical column. Any levels in the test dataset that are not available in the training dataset are mapped to this additional level.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained classification model|  

## See also

 [Classification](machine-learning-initialize-model-classification.md)   
 [Two-Class Logistic Regression](two-class-logistic-regression.md)   
 [A-Z Module List](a-z-module-list.md)
