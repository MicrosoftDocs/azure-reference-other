---
title: "Poisson Regression | Microsoft Docs"
ms.custom: ""
ms.date: 08/30/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 80e21b9d-3827-40d8-b733-b53148becbc2
caps.latest.revision: 24
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlun"
---
# Poisson Regression
*Creates a regression model that assumes data has a Poisson distribution*  
  
 Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)  
  
##  <a name="Remarks"></a> Module Overview  

This article describes how to use the **Poisson Regression** module in Azure Machine Learning Studio to create a Poisson regression model. 

 After you have configured the model, you must train the model using a dataset that contains an example of the value you want to predict (a column that contains the numeric outcome), using either [Train Model](train-model.md) or [Tune Model Hyperparameters](tune-model-hyperparameters.md).  The trained model can then be used to make predictions using [Score Model](score-model.md). 

Poisson regression is intended for use in regression models that are used to predict numeric values, typically counts. Therefore, you should use this module to create your regression model only if the values you are trying to predict fit the following conditions:  
  
-   The response variable has a [Poisson distribution](http://en.wikipedia.org/wiki/Poisson_distribution).  
  
-   Counts cannot be negative. The method will fail outright if you attempt to use it with negative labels.  
  
-   Given that a Poisson distribution is a discrete distribution, it is not meaningful to use this method with non-whole numbers.  
  
> [!TIP]
> If your target isn’t a count, Poisson regression is probably not an appropriate method. Try one of the other modules in this category. For help picking a regression method, see the [Azure machine Learning algorithm cheat sheet](https://docs.microsoft.com/azure/machine-learning/machine-learning-algorithm-cheat-sheet). 
  

## What is Poisson regression?

 Poisson regression is a special type of regression analysis that is typically used to model counts. For example, Poisson regression would be useful in these scenarios:  
  
- Modeling the number of colds associated with airplane flights  
  
- Estimating the number of emergency service calls during an event

- Projecting the number of customer inquiries subsequent to a promotion  
  
- Creating contingency tables  

 Because the response variable has a Poisson distribution, the underlying assumptions about probability distribution are different from least-squares regression and Poisson models must be interpreted differently from other regression models.  
  
 See the [Technical Notes](#bkmk_Notes) section for more details of the formulas.  

  
## How to Configure a Poisson Regression Model  

  
1.  Add the **Poisson Regression** module to your experiment.  

2. Add a training dataset. We recommend that you use [Normalize Data](normalize-data.md) to normalize the input dataset before using it to train the regressor.  
  
3.  In the **Properties** pane of the **Poisson Regression** module, specify how you want the model to be trained, by setting the **Create trainer mode** option.  
  
    -   **Single Parameter**.                   If you know how you want to configure the model, you can provide a specific set of values as arguments.  
  
    -   **Parameter Range**. If you are not sure of the best parameters, you can find the optimal parameters by specifying multiple values and using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to find the optimal configuration.  
  
         After you have set a range of values, the trainer iterates over multiple combinations of settings and finds the model with the best combination of values.  
  
4.  For **Optimization tolerance**, type a value that defines the tolerance interval during optimization.  
  
     The lower the value, the slower and more accurate the fitting.  
  
5.  In the options, **L1 regularization weight** and **L2 regularization weight**, type values to use for L1 and L2 regularization.  
  
     *Regularization* adds constraints to the algorithm regarding aspects of the model that are independent of the training data.   Regularization is commonly used to avoid overfitting. In this module, you can apply a combination of L1 and L2 regularizations.  
  
    -   L1 regularization is useful if the goal is to have a model that is as sparse as possible.  
  
         L1 regularization is done by subtracting the L1 weight of the weight vector from the loss expression that the learner is trying to minimize. The L1 norm is a good approximation to the L0 norm, which is the number of non-zero coordinates.  
  
    -   L2 regularization prevents any single coordinate in the weight vector from growing too much in magnitude. L2 regularization is useful if the goal is to have a model with small overall weights.  
  
     By combining L1 and L2 regularization, you can impose a penalty on the magnitude of the parameter values. The learner tries to minimize the penalty, in a tradeoff with minimizing the loss.  
  
     For a general discussion of L1 and L2 regularization, see [L1 and L2 Regularization for Machine Learning](https://msdn.microsoft.com/magazine/dn904675.aspx).  
  
6.  For **Memory size for L-BFGS**, specify the amount of memory to reserve for model fitting and optimization.  
  
     L-BFGS is a technique used for optimization. The technique is based on the Broyden–Fletcher–Goldfarb–Shanno (BFGS) algorithm, and specifies a limited amount of memory (L) to compute the next step direction.  
  
     By changing this parameter, you can affect the number of past positions and gradients that are stored for computation of the next step.  
  
7.  Connect the training dataset to the righthand input of the module used for training, and connect the untrained Poisson regression model to the lefthand input: 
  
    -   If you set **Create trainer mode** to **Single Parameter**, add a tagged dataset and train the model by using the [Train Model](train-model.md) module.  
  
    -   If you set **Create trainer mode** to **Parameter Range**, connect a tagged dataset and train the model by using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.  
  
    > [!WARNING]
    >  -   If you pass a parameter range to [Train Model](train-model.md), it will use only the first value in the parameter range list.  
    > -   If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.  
    > -   If you select the **Parameter Range** option and enter a single value for any parameter, that single value you specified will be used throughout the sweep, even if other parameters change across a range of values.  

8.  Run the experiment to train the model. 
    
## Examples  

For examples of how Poisson regression is used in machine learning, see these sample experiments in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com).  
  
-   [Sample 6: Train, Test, Evaluate for Regression: Auto Imports Dataset](https://gallery.cortanaintelligence.com/Experiment/670fbfc40c4f44438bfe72e47432ae7a?r=legacy): This experiment compares the outcomes of two algorithms:  **Poisson Regression** and [Decision Forest Regression](decision-forest-regression.md).  
  
-   The [Preventive Maintenance](https://gallery.cortanaintelligence.com/Experiment/a677f8eececf40eaa158699a2b27e3c8?r=legacy) sample is an extended walkthrough that uses **Poisson Regression** to assess the severity of failures predicted by a decision forest model.  
  
##  <a name="bkmk_Notes"></a> Technical Notes  
 
 Poisson regression is used to model count data, assuming that the label has a Poisson distribution. For example, you might use it to predict the number of calls to a customer support center on a particular day.
  
 For this algorithm, it is assumed that an unknown function, denoted Y, has a Poisson distribution. The Poisson distribution is defined as follows:  
  
 Given the instance x = (x0, …, xd-1), for every k=0,1, …, the probability that the value of the instance is k is:  
  
 Given the set of training examples, the algorithm tries to find the optimal values for θ0, …,θD-1 by trying to maximize the log likelihood of the parameters. The likelihood of the parameters θ0, …,θD-1 is the probability that the training data was sampled from a distribution with these parameters.  
  
 The log probability can be viewed as log*p*(y = yi)  
  
 The prediction function outputs the expected value of that parameterized Poisson distribution, specifically:  *f*w,b(x) = E[Y&#124;x] = e<sup>w</sup><sup>T</sup><sup>x+b</sup>.  
  
 For more information, see the entry for [Poisson regression](https://wikipedia.org/wiki/Poisson_regression) in Wikipedia.  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Optimization tolerance|>=double.Epsilon|Float|0.0000001|Specify a tolerance value for optimization convergence. The lower the value, the slower and more accurate the fitting.|  
|L1 regularization weight|>=0.0|Float|1.0|Specify the L1 regularization weight. Use a non-zero value to avoid overfitting the model.|  
|L2 regularization weight|>=0.0|Float|1.0|Specify the L2 regularization weight. Use a non-zero value to avoid overfitting the model.|  
|Memory size for L-BFGS|>=1|Integer|20|Indicate how much memory (in MB) to use for the L-BFGS optimizer. With less memory, training is faster but less accurate the training.|  
|Random number seed|any|Integer||Type a value to seed the random number generator used by the model. Leave blank for default.|  
|Allow unknown categorical levels|any|Boolean|true|Indicate whether an additional level should be created for each categorical column. Any levels in the test dataset not available in the training dataset are mapped to this additional level.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained regression model|  
  
## See Also  
 [Regression](machine-learning-initialize-model-regression.md)   
 [A-Z Module List](a-z-module-list.md)