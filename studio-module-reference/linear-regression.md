---
title: "Linear Regression | Microsoft Docs"
ms.custom: ""
ms.date: 06/13/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 31960a6f-789b-4cf7-88d6-2e1152c0bd1a
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Linear Regression
*Creates a linear regression model*  
  
 Category: [Machine Learning / Initialize Model / Regression](machine-learning-initialize-model-regression.md)  
  
##  <a name="Remarks"></a> Module Overview  
 
 This article describes how to use the **Linear Regression** module in Azure Machine Learning to create a linear regression model for use in an experiment.  
  
 Regression is a machine learning used to predict a numeric outcome. Linear regression attempts to establish a linear relationship between one or more independent variables and an outcome, or *dependent variable*.   
  
 After you have configured the model, you must train the model using a labeled dataset and the [Train Model](train-model.md) module. If you use the online gradient descent method, you can also train the model using [Tune Model Hyperparameters](tune-model-hyperparameters.md) to automatically optimize the model parameters .  
  
 The trained model can then be used to make predictions. Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.  
  
## Understanding Linear Regression  

 There are many different types of regression. In the most basic sense, regression means predicting a numeric target.  However, for years statisticians have been developing increasingly advanced methods for regression. Linear regression is still a good choice when you want a very simple model for a basic predictive task. Linear regression also tends to work well on high-dimensional, sparse data sets lacking complexity.  
  
 In Azure Machine Learning Studio, you can use linear regression to solve these regression problems:  
  
-   The classic regression problem involves a single independent variable and a dependent variable. This is called *simple regression*.  
  
-   *Multiple linear regression* involves two or more independent variables that contribute to a single dependent variable. The **Linear Regression** module can solve such problems, in which multiple inputs are used to predict a single numeric outcome, also called *multivariate linear regression*.  
  
 The task of predicting multiple dependent variables within a single model is called *multi-label regression*. For example, in multi-label logistic regression, a sample can be assigned to multiple different labels. This type of regression is not supported in Azure Machine Learning; instead, you must create a separate learner for each output that you wish to predict. 
 
  The **Linear Regression** module in Azure Machine Learning can use two methods to fit the linear model:
 
+ **Online gradient descent**  
  
     Gradient descent is a method that minimizes the amount of error at each step of the model training process. There are many variations on gradient descent and its optimization for various learning problems has been extensively studied.  
  
     If you choose this option for **Solution method**, you can set a variety of parameters to control the step size, learning rate, and so forth. This option also supports use of an integrated parameter sweep.  
     
+ **Ordinary least squares**.  
  
     Least squares linear regression is one of the most commonly used techniques in predictive analytics. This method assumes that there is a fairly strong linear relationship between the inputs and the dependent variable. Ordinary least squares refers to the loss function, which computes error as the sum of the square of distance from the actual value to the predicted line, and fits the model by minimizing the squared error.  
  
     Least squares is also the method that is used in the Analysis Toolpak for Microsoft Excel.
      
  
## How to Configure a Linear Regression Model  

The options available in this module change depending on the method you select for fitting the regression line:   

+ [To create a regression model using Online Gradient Descent](#bkmk_GradientDescent)  

+ [To create a regression model using Ordinary Least Squares](#bkmk_OrdinaryLeastSquares)  
  
For small datasets, it is best to select Ordinary Least Squares. This should give very similar results to Excel.  

Gradient descent is a better loss function for models that are more complex, or that have too little training data given the number of variables.  
  
###  <a name="bkmk_OrdinaryLeastSquares"></a> Create a regression model using Ordinary Least Squares  
  
1.  Add the **Linear Regression Model** module to your experiment.  You can find the module in Azure Machine Learning Studio in the **Machine Learning** category. Expand the **Initialize Model** category, expand **Regression**, and then drag the **Linear Regression Model** module to your experiment
  
2.  In the **Properties** pane, in the **Solution method** dropdown list, select **Ordinary Least Squares**. This option specifies the computation method used to find the regression line.  
  
3.  In **L2 regularization weight**, type the value to use as the weight for L2 regularization. We recommend that you use a non-zero value to avoid overfitting.  
  
     To learn more about how regularization affects model fitting, see this article: [L1 and L2 Regularization for Machine Learning](https://msdn.microsoft.com/magazine/dn904675.aspx)  
  
4.  Select the option, **Include intercept term**, if you want to view the term for the intercept.  
  
     Deselect this option if you don't need to review the regression formula.  
  
5.  For **Random number seed**, you can optionally type a value to seed the random number generator used by the model.  
  
     Using a seed value is useful if you want to maintain the same results across different runs of the same experiment.  
  
6.  Deselect the option, **Allow unknown categorical levels**, if you want missing values to raise an error.  
  
     If this option is selected, an additional level will be created for each categorical column, and any levels in the test dataset not available in the training dataset are mapped to this additional level.  
  
7.  Run the experiment.  
  

After the model has been trained, you can view the model's parameters by right-clicking the trainer output and selecting **Visualize**.  
  
You also can connect the trained model to the [Score Model](score-model.md) module to make predictions, or pass the untrained model to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.  
  
###  <a name="bkmk_GradientDescent"></a> Create a regression model using Online Gradient Descent  
  
1.  Add the **Linear Regression Model** module to your experiment.  You can find the module in Azure Machine Learning Studio in the **Machine Learning** category. Expand the **Initialize Model** category, expand **Regression**, and then drag the **Linear Regression Model** module to your experiment
  
2.  In the **Properties** pane, in the **Solution method** dropdown list, choose **Online Gradient Descent** as the computation method used to find the regression line.  
  
3.  For **Create trainer mode**, indicate whether you want to train the model with a predefined set of parameters, or if you want to optimize the model by using a parameter sweep.  
  
    -   **Single Parameter**  
  
         If you know how you want to configure the linear regression network, you can provide a specific set of values as arguments.  
  
         You must then train the model by using a tagged dataset and the [Train Model](train-model.md) module.  
  
    -   **Parameter Range**  
  
         If you want the algorithm to find the best parameters, set **Create trainer mode** option to **Parameter Range**, specifying multiple values  
  
         You should then train the model using [Tune Model Hyperparameters](tune-model-hyperparameters.md) and a tagged dataset.  The algorithm will determine the optimal parameters for you. You can save the model trained using those parameters, or you can make a note of the parameter settings to use when configuring a learner.  
  
    If you configure the model with specific values using the **Single Parameter** option and then switch to the **Parameter Range** option, the model will be trained using the minimum value in the range for each parameter.  
    
    Conversely, if you configure specific settings when you create the model but select the **Parameter Range** option and use a [Tune Model Hyperparameters](tune-model-hyperparameters.md), the model will be trained using the default values for the learner as the range of values to sweep over.  
  
4.  For **Learning rate**, specify the initial learning rate for the stochastic gradient descent optimizer.  
  
5.  For **Number of training epochs**, type a value that indicates how many times the algorithm should iterate through examples.  
  
     For datasets with a small number of examples, this number should be large to reach convergence.  
  
6.  If you have already normalized the numeric data used to train the model, deselect the option, **Normalize features**. Otherwise the module will by default normalize all numeric inputs to a range between 0 and 1.  
  
     Note that when you pass new data to the model for scoring, you should use the same normalization method.  
  
7.  In **L2 regularization weight**, type the value to use as the weight for L2 regularization. We recommend that you use a non-zero value to avoid overfitting.  
  
     To learn more about how regularization affects model fitting, see this article: [L1 and L2 Regularization for Machine Learning](https://msdn.microsoft.com/magazine/dn904675.aspx)  
  
8.  Select the option, **Normalize features**, to indicate that instances should be normalized.  
  
9. Select the option, **Average final hypothesis**, to average the final hypothesis.  
  
     In regression models, hypothesis testing means using some statistic to evaluate the probability of the null hypothesis, which states that there is no linear correlation between a dependent and independent variable.  
  
     In many regression problems, you must test a hypothesis involving more than one variable. This option, which is selected by default, tests a combination of the parameters where two or more parameters are involved.  
  
10. Select the option, **Decrease learning rate**, if you want the learning rate to decrease as iterations progress.  
  
11. For **Random number seed**, you can optionally type a value to seed the random number generator used by the model.  
  
     Using a seed value is useful if you want to maintain the same results across different runs of the same experiment.  
  
12. Deselect the option, **Allow unknown categorical levels**, if you want missing values to raise an error.  
  
     When this option is selected, an additional level will be created for each categorical column, and any levels in the test dataset not available in the training dataset are mapped to this additional level.  
  
13. Run the experiment.  
  
After the model has been trained, you can connect it to the [Score Model](score-model.md) module to make predictions.  
  
Alternatively, the untrained model can be passed to [Cross-Validate Model](cross-validate-model.md) for cross-validation against a labeled data set.  
  
## Examples  

 For examples of regression models, see these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Compare Regressors](http://go.microsoft.com/fwlink/?LinkId=525731) sample contrasts several different kinds of regression models.  
  
-   The [Cross Validation for Regression](http://go.microsoft.com/fwlink/?LinkId=525735) sample demonstrates linear regression using ordinary least squares.  
  
-   The [Twitter sentiment analysis](http://go.microsoft.com/fwlink/?LinkId=525274) sample uses several different regression models to generate predicted ratings.  
  
## Technical Notes  

 Many tools support creation of linear regression, ranging from the simple to complex. For example, you can easily perform linear regression in Excel, using the Solver Toolpak, or you can code your own regression algorithm, using R, Python, or C#. 
 
 However, because linear regression is a well-established technique that is supported by many different tools, there are many different interpretations and implementations. Not all types of models are supported equally by all tools. There are also some differences in nomenclature you should be aware of. 
 
 - Regression methods are often categorized by the number of response variables.  For example, multiple linear regression means a model that has multiple variables to predict. 
 
   In Matlab, multivariate regression refers to a model that has multiple response variables. 
 
   In Azure Machine Learning, regression models support a single response variable.  
  
In the R language, the features provided for linear regression depend on the package you are using. For example, the **glm** package will give you the ability to create a logistic regression model with multiple independent variables.  In general, Azure Machine Learning Studio provides the same functionality as the R **glm** package. 
   
> [!TIP]
> We recommend that you use this module, **Linear Regression**, for typical regression problems. 
> 
> In contrast, if you are using multiple variables to predict a class value, we recommend the [Two-Class Logistic Regression](two-class-logistic-regression.md) or [Multiclass Logistic Regression](multiclass-logistic-regression.md) modules.  
>   
> If you want to use other linear regression packages that are available for the R language, we recommend that you use the [Execute R Script](execute-r-script.md) module and call the **lm** or **glm** packages, which are included in the runtime environment of Azure Machine Learning Studio.   
  
##  <a name="parameters"></a> Module Parameters  
  
###  
  
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
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained regression model|  
  
## See Also  
 [A-Z Module List](a-z-module-list.md)   
 [Regression](machine-learning-initialize-model-regression.md)