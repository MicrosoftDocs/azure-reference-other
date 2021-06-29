---
title: "ML Studio (classic): Linear Regression - Azure"
description: Learn how to use the Linear Regression module to create a linear regression model for use in an experiment.  
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Linear Regression

*Creates a linear regression model*

Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Linear Regression** module in Machine Learning Studio (classic), to create a linear regression model for use in an experiment.  Linear regression attempts to establish a linear relationship between one or more independent variables and a numeric outcome, or dependent variable. 

You use this module to define a linear regression method, and then train a model using a labeled dataset. The trained model can then be used to make predictions. Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.

## More about linear regression

Linear regression is a common statistical method, which has been adopted in machine learning and enhanced with many new methods for fitting the line and measuring error. In the most basic sense, regression refers to prediction of a numeric target. Linear regression is still a good choice when you want a very simple model for a basic predictive task. Linear regression also tends to work well on high-dimensional, sparse data sets lacking complexity.

Machine Learning Studio (classic) supports a variety of regression models, in addition to linear regression. However, the term "regression" can be interpreted loosely, and some types of regression provided in other tools are not supported in Studio (classic).

+ The classic regression problem involves a single independent variable and a dependent variable. This is called *simple regression*.  This module supports simple regression.

+ *Multiple linear regression* involves two or more independent variables that contribute to a single dependent variable. Problems in which multiple inputs are used to predict a single numeric outcome are also  called *multivariate linear regression*.

    The **Linear Regression** module can solve these problems, as can most of the other regression modules in Studio (classic).

+ *Multi-label regression* is the task of predicting multiple dependent variables within a single model. For example, in multi-label logistic regression, a sample can be assigned to multiple different labels. (This is different from the task of predicting multiple levels within a single class variable.)

    This type of regression is not supported in Machine Learning. To predict multiple variables, create a separate learner for each output that you wish to predict.

For years statisticians have been developing increasingly advanced methods for regression. This is true even for linear regression. This module supports two methods to measure error and fit the regression line: ordinary least squares method, and gradient descent.

- **Gradient descent** is a method that minimizes the amount of error at each step of the model training process. There are many variations on gradient descent and its optimization for various learning problems has been extensively studied. If you choose this option for **Solution method**, you can set a variety of parameters to control the step size, learning rate, and so forth. This option also supports use of an integrated parameter sweep.

- **Ordinary least squares** is one of the most commonly used techniques in linear regression. For example, least squares is the method that is used in the Analysis Toolpak for Microsoft Excel.

    Ordinary least squares refers to the loss function, which computes error as the sum of the square of distance from the actual value to the predicted line, and fits the model by minimizing the squared error. This method assumes a strong linear relationship between the inputs and the dependent variable.

## How to configure Linear Regression

This module supports two methods for fitting a regression model, with very different options:

+ [Create a regression model using online gradient descent](#bkmk_GradientDescent)

    Gradient descent is a better loss function for models that are more complex, or that have too little training data given the number of variables.

    This option also supports a parameter sweep, if you train the model using [Tune Model Hyperparameters](tune-model-hyperparameters.md) to automatically optimize the model parameters.

+ [Fit a regression model using ordinary least squares](#bkmk_OrdinaryLeastSquares)

    For small datasets, it is best to select ordinary least squares. This should give very similar results to Excel.

### <a name="bkmk_OrdinaryLeastSquares"></a> Create a regression model using ordinary least squares

1. Add the **Linear Regression Model** module to your experiment in Studio (classic).

    You can find this module in the **Machine Learning** category. Expand **Initialize Model**, expand **Regression**, and then drag the **Linear Regression Model** module to your experiment.

2. In the **Properties** pane, in the **Solution method** dropdown list, select **Ordinary Least Squares**. This option specifies the computation method used to find the regression line.

3. In **L2 regularization weight**, type the value to use as the weight for L2 regularization. We recommend that you use a non-zero value to avoid overfitting.

     To learn more about how regularization affects model fitting, see this article: [L1 and L2 Regularization for Machine Learning](https://msdn.microsoft.com/magazine/dn904675.aspx)

4. Select the option, **Include intercept term**, if you want to view the term for the intercept.

    Deselect this option if you don't need to review the regression formula.

5. For **Random number seed**, you can optionally type a value to seed the random number generator used by the model.

    Using a seed value is useful if you want to maintain the same results across different runs of the same experiment. Otherwise, the default is to use a value from the system clock.

6. Deselect the option, **Allow unknown categorical levels**, if you want missing values to raise an error.

    If this option is selected, an additional level is created for each categorical column. Any levels in the test dataset that were not present in the training dataset are mapped to this additional level.

7. Add the [Train Model](train-model.md) module to your experiment, and connect a labeled dataset.

8. Run the experiment.

### Results for ordinary least squares model

After training is complete:

+ To view the model's parameters, right-click the trainer output and select **Visualize**.

+ To make predictions, connect the trained model to the [Score Model](score-model.md) module, along with a dataset of new values. 

+ To perform cross-validation against a labeled data set, connect the untrained model to [Cross-Validate Model](cross-validate-model.md).

### <a name="bkmk_GradientDescent"></a> Create a regression model using online gradient descent

1. Add the **Linear Regression Model** module to your experiment in Studio (classic).

    You can find this module in the **Machine Learning** category. Expand **Initialize Model**, expand **Regression**, and drag the **Linear Regression Model** module to your experiment

2. In the **Properties** pane, in the **Solution method** dropdown list, choose **Online Gradient Descent** as the computation method used to find the regression line.

3. For **Create trainer mode**, indicate whether you want to train the model with a predefined set of parameters, or if you want to optimize the model by using a parameter sweep.

    + **Single Parameter**: If you know how you want to configure the linear regression network, you can provide a specific set of values as arguments.

    + **Parameter Range**: If you want the algorithm to find the best parameters for you, set **Create trainer mode** option to **Parameter Range**. You can then specify multiple values for the algorithm to try.

4. For **Learning rate**, specify the initial learning rate for the stochastic gradient descent optimizer.

5. For **Number of training epochs**, type a value that indicates how many times the algorithm should iterate through examples. For datasets with a small number of examples, this number should be large to reach convergence.

6. **Normalize features**: If you have already normalized the numeric data used to train the model, you can deselect this option. By default, the module normalizes all numeric inputs to a range between 0 and 1.

    > [!NOTE]
    > 
    > Remember to apply the same normalization method to new data used for scoring.

7. In **L2 regularization weight**, type the value to use as the weight for L2 regularization. We recommend that you use a non-zero value to avoid overfitting.

    To learn more about how regularization affects model fitting, see this article: [L1 and L2 Regularization for Machine Learning](https://msdn.microsoft.com/magazine/dn904675.aspx)

8. Select the option, **Average final hypothesis**, to average the final hypothesis.

    In regression models, hypothesis testing means using some statistic to evaluate the probability of the null hypothesis, which states that there is no linear correlation between a dependent and independent variable.  In many regression problems, you must test a hypothesis involving more than one variable.

    This option is enabled by default, meaning the algorithm tests a combination of the parameters where two or more parameters are involved.

9. Select the option, **Decrease learning rate**, if you want the learning rate to decrease as iterations progress.  

10. For **Random number seed**, you can optionally type a value to seed the random number generator used by the model. Using a seed value is useful if you want to maintain the same results across different runs of the same experiment.

11. Deselect the option, **Allow unknown categorical levels**, if you want missing values to raise an error.

    When this option is selected, an additional level is created for each categorical column. Any levels in the test dataset not present in the training dataset are mapped to this additional level.

12. Add a labeled dataset and one of the [training modules](machine-learning-train.md).

    If you are not using a parameter sweep, use the [Train Model](train-model.md) module.

    To have the algorithm find the best parameters for you, train the model using [Tune Model Hyperparameters](tune-model-hyperparameters.md).

    > [!NOTE]
    > If you configure the model with specific values using the **Single Parameter** option and then switch to the **Parameter Range** option, the model is trained using the minimum value in the range for each parameter.  
    > 
    > Conversely, if you configure specific settings when you create the model but select the **Parameter Range** option, the model is trained using the default values for the learner as the range of values to sweep over.

13. Run the experiment.

### Results for online gradient descent

After training is complete:

+ To make predictions, connect the trained model to the [Score Model](score-model.md) module, together with new input data.
+ To perform cross-validation against a labeled data set, connect the untrained model to [Cross-Validate Model](cross-validate-model.md).

## Examples

For examples of regression models, see these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/):

+ [Compare Regressors](https://go.microsoft.com/fwlink/?LinkId=525731): Contrasts several different kinds of regression models.

+ [Cross Validation for Regression](https://go.microsoft.com/fwlink/?LinkId=525735): Demonstrates linear regression using ordinary least squares.

+ [Twitter sentiment analysis](https://go.microsoft.com/fwlink/?LinkId=525274): Uses several different regression models to generate predicted ratings.

## Technical notes  

This section contains implementation details, tips, and answers to frequently asked questions.

### Usage tips

Many tools support creation of linear regression, ranging from the simple to complex. For example, you can easily perform linear regression in Excel, using the Solver Toolpak, or you can code your own regression algorithm, using R, Python, or C#.

However, because linear regression is a well-established technique that is supported by many different tools, there are many different interpretations and implementations. Not all types of models are supported equally by all tools. There are also some differences in nomenclature to observe.

+ Regression methods are often categorized by the number of response variables.  For example, multiple linear regression means a model that has multiple variables to predict.

+ In Matlab, multivariate regression refers to a model that has multiple response variables.

+ In Machine Learning, regression models support a single response variable.

+ In the R language, the features provided for linear regression depend on the package you are using. For example, the **glm** package will give you the ability to create a logistic regression model with multiple independent variables.  In general, Machine Learning Studio (classic) provides the same functionality as the R **glm** package.

We recommend that you use this module, **Linear Regression**, for typical regression problems.

In contrast, if you are using multiple variables to predict a class value, we recommend the [Two-Class Logistic Regression](two-class-logistic-regression.md) or [Multiclass Logistic Regression](multiclass-logistic-regression.md) modules.

If you want to use other linear regression packages that are available for the R language, we recommend that you use the [Execute R Script](execute-r-script.md) module and call the **lm** or **glm** packages, which are included in the runtime environment of Machine Learning Studio (classic).

## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Normalize features|any|Boolean|true|Indicate whether instances should be normalized|  
|Average final hypothesis|any|Boolean|true|Indicate whether the final hypothesis should be averaged|  
|Learning rate|>=double.Epsilon|Float|0.1|Specify the initial learning rate for the stochastic gradient descent optimizer|  
|Number of training epochs|>=0|Integer|10|Specify how many times the algorithm should iterate through examples. For datasets with a small number of examples, this number should be large to reach convergence.|  
|Decrease learning rate|Any|Boolean|true|Indicate whether the learning rate should decrease as iterations progress|  
|L2 regularization weight|>=0.0|Float|0.001|Specify the weight for L2 regularization. Use a non-zero value to avoid overfitting.|  
|Random number seed|any|Integer||Specify a value to seed the random number generator used by the model. Leave blank for default.|  
|Allow unknown categorical levels|any|Boolean|true|Indicate whether an additional level should be created for each categorical column. Any levels in the test dataset not available in the training dataset are mapped to this additional level.|  
|Include intercept term|Any|Boolean|True|Indicate whether an additional term should be added for the intercept|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained regression model|  

## See also

 [Regression](machine-learning-initialize-model-regression.md)
