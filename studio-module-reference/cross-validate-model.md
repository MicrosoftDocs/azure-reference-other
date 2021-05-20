---
title: "ML Studio (classic): Cross-Validate Model - Azure"
description: Learn how to use the Cross-Validate Model module to assess the variability of a dataset and the reliability of a model trained using that data.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Cross-Validate Model
*Cross-validates parameter estimates for classification or regression models by partitioning the data*  
  
 Category: [Machine Learning / Evaluate](machine-learning-evaluate.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the **Cross-Validate Model** module in Azure Machine Learning Studio (classic). *Cross-validation* is an important technique often used in machine learning to assess both the variability of a dataset and the reliability of any model trained using that data.  
  
The **Cross-Validate Model** module takes as input a labeled dataset, together with an untrained classification or regression model. It divides the dataset into some number of subsets (*folds*), builds a model on each fold, and then returns a set of accuracy statistics for each fold. By comparing the accuracy statistics for all the folds, you can interpret the quality of the data set and understand whether the model is susceptible to variations in the data.  
  
Cross-validate also returns predicted results and probabilities for the dataset, so that you can assess the reliability of the predictions.  
  
### How cross-validation works
  
1. Cross validation randomly divides the training data into a number of partitions, also called *folds*. 

    + The algorithm defaults to 10 folds if you have not previously partitioned the dataset. 
    + To divide the dataset into a different number of folds, you can use the [Partition and Sample](partition-and-sample.md) module and indicate how many folds to use.  
  
2.  The module sets aside the data in fold 1 to use for validation (this is sometimes called the *holdout fold*), and uses the remaining folds to train a model. 

    For example, if you create five folds, the module would generate five models during cross-validation, each model trained using 4/5 of the data, and tested on the remaining 1/5.  
  
2.  During testing of the model for each fold, multiple accuracy statistics are evaluated. Which statistics are used depends on the type of model that you are evaluating. Different statistics are used to evaluate classification models vs. regression models.  
  
3.  When the building and evaluation process is complete for all folds, **Cross-Validate Model** generates a set of performance metrics and scored results for all the data. You should review these metrics to see whether any single fold has particularly high or low accuracy 

### Advantages of cross-validation
  
A different, and very common way of evaluating a model is to divide the data into a training and test set using [Split Data](split-data.md), and then validate the model on the training data. However, cross-validation offers some advantages:  
  
-   Cross-validation uses more test data.
  
     Cross-validation measures the performance of the model with the specified parameters in a bigger data space. That is, cross-validation uses the entire training dataset for both training and evaluation, instead of some portion. In contrast, if you validate a model by using data generated from a random split, typically you evaluate the model only on 30% or less of the available data.  
  
     However, because cross-validation trains and validates the model multiple times over a larger dataset, it is much more computationally intensive and takes much longer than validating on a random split.  
  
-   Cross-validation evaluates the dataset as well as the model.
  
     Cross-validation does not simply measure the accuracy of a model, but also gives you some idea of how representative the dataset is and how sensitive the model might be to variations in the data.  
  
## How to use Cross-Validate Model

There are two main ways to use cross-validation. 

+ [For simple evaluation](#bkmk_simple)
+ [In combination with a parameter sweep](#bkmk_sweep) 

Cross-validation can take a long time to run if you use a lot of data.  Therefore, you might use **Cross-Validate Model** in the initial phase of building and testing your model, to evaluate the goodness of the model parameters (assuming that computation time is tolerable), and then train and evaluate your model using the established parameters with the [Train Model](train-model.md) and [Evaluate Model](evaluate-model.md) modules.

### <a name ="bkmk_simple"></a>Simple cross-validation

In this scenario, you both train and test the model using **Cross Validate Model**.

1. Add the **Cross Validate Model** module to your experiment. You can find it in Azure Machine Learning Studio (classic), in the **Machine Learning** category, under **Evaluate**. 

2. Connect the output of any [classification](machine-learning-initialize-model-classification.md) or [regression](machine-learning-initialize-model-regression.md) model. 

    For example, if you are using a **Two Class Bayes Point Machine** for classification, configure the model with the parameters you want, and then drag a connector from the **Untrained model** port of the classifier to the matching port of **Cross Validate Model**. 

    > [!TIP] 
    > The model need not be trained because **Cross-Validate Model** automatically trains the model as part of evaluation.  
  
2.  On the **Dataset** port of **Cross Validate Model**, connect any labeled training dataset.  
  
3.  In the **Properties** pane of **Cross Validate Model**, click **Launch column selector** and choose the single column that contains the class label, or the predictable value. 

4. Set a value for the **Random seed** parameter if you want to be able to repeat the results of cross-validation across successive runs on the same data.  
  
5.  Run the experiment.

6. See the [Results](#Results) section for a description of the reports.

    To get a copy of the model for re-use later, right click the output of the module that contains the algorithm (for example, the **Two Class Bayes Point Machine**), and click **Save as Trained Model**.

### <a name ="bkmk_sweep"></a>Cross-validation with a parameter sweep

In this scenario, you use [Tune Model Hyperparameters](tune-model-hyperparameters.md) to identify the best model by conducting a parameter sweep, and then use **Cross Validate Model** to check its reliability. This is the easiest way to have Azure Machine Learning identify the best model and then generate metrics for it.

1. Add the dataset for model training, and add one of the machine learning modules that creates a classification or regression model.

2. Add the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to your experiment. You can find it in the **Machine Learning** category, under **Train**. 

3. Attach the classification or regression model to the **Untrained model** input of [Tune Model Hyperparameters](tune-model-hyperparameters.md).

4. Add the **Cross Validate Model** module to your experiment. You can find it in Azure Machine Learning Studio (classic), in the **Machine Learning** category, under **Evaluate**. 

5. Locate the **Trained best model** output of **Tune Model Hyperparameters**, and connect it to the **Untrained model** input of **Cross Validate Model**.

6. Connect the training data to the **Training dataset** input of **Cross Validate Model**. 

7. Run the experiment.

8. After reviewing the results, and the evaluation scores, to get a copy of the best model for later re-use, just right-click the  **Tune Model Hyperparameters** module, select **Trained best model**, and then click **Save as Trained Model**.

> [!NOTE]
You might get different results if you use the input on the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module for **Optional validation dataset**. 
> 
> That is because when you use this option, you are in effect specifying a static training dataset and testing dataset. Hence, the cross-validation process also uses the specified training and testing datasets, rather than splitting the data into *n* groups for training and testing. However, metrics are generated on an *n*-fold basis.

## <a name="Results"></a> Results

After all iterations are complete, **Cross-Validate Model** creates scores for the entire dataset, as well as performance metrics you can use to assess the quality of the model.
 
### Scored results

The first output of the module provides the source data for each row, together with some predicted values and related probabilities. 

To view these results, in the experiment, right-click the **Cross-Validate Model** module, select **Scored results**, and click **Visualize**.
 
| New column name|Description| 
|----|----|
|Fold Assignments |Indicates the 0-based index of the fold each row of data was assigned to during cross-validation.|  
|Scored Labels |This column is added at the end of the dataset, and contains the predicted value for each row|
|Scored Probabilities| This column is added at the end of the dataset, and indicates the estimated probability of the value in **Scored Labels**.|  

 ### Evaluation results

The second report is grouped by folds. Remember that, during execution, **Cross-Validate Model** randomly splits the training data into *n* folds (by default, 10). In each iteration over the dataset, **Cross-Validate Model** uses one fold as a validation dataset, and uses the remaining *n-1* folds to train a model. Each of the *n* models is tested against the data in all the other folds.

In this report, the folds are listed by index value, in ascending order.  To order on any other column you can save the results as a dataset.

To view these results, in the experiment, right-click the **Cross-Validate Model** module, select **Evaluation results by fold**, and click **Visualize**.


|Column name| Description|
|----|----|
|Fold number| An identifier for each fold. If you created 5 folds, there would be 5 subsets of data, numbered 0 to 4.
|Number of examples in fold|The number of rows assigned to each fold. They should be roughly equal. |
|Model|The algorithm used in the model, identified by the API name|

Additionally, the following metrics are included for each fold, depending on the type of model that you are evaluating. 

+ **Classification models**: Precision, recall, F-score, AUC, average log loss, training log loss  

+ **Regression models**: Negative log likelihood, mean absolute error, root mean squared error, relative absolute error, and coefficient of determination
 
##  Examples  

For examples of how cross-validation is used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Cross validation for binary classifier](https://go.microsoft.com/fwlink/?LinkId=525734): Demonstrates how to use cross-validation with a binary classification model.
  
- [Cross Validation Regression: Auto Imports Dataset](https://go.microsoft.com/fwlink/?LinkId=525735): Demonstrates how to use cross validation with regression models and how to interpret the results.  

## Technical notes  

+ It is a best practice to normalize datasets before using them for cross-validation. 

+ Because **Cross-Validate Model** trains and validates the model multiple times, it is much more computationally intensive and takes longer to complete than if you validated the model using a randomly divided dataset. 

+ We recommend that you use **Cross-Validate Model** to establish the goodness of the model given the specified parameters. Use [Tune Model Hyperparameters](tune-model-hyperparameters.md) to identify the optimal parameters. 

+ There is no need to split the dataset into training and testing sets when you use cross validation to measure the accuracy of the model. 

    However, if a validation dataset is provided upstream, the module uses the specified training and testing datasets instead of splitting into *n* folds. That is, the first dataset is used to train the model for each parameter combination, and the models are evaluated on the validation dataset. See the section on [using a parameter sweep with cross-validation](#bkmk_sweep).

+ Although this article uses older versions of the modules, it has a good explanation of the cross-validation process: [How to choose parameters to optimize your algorithms in Azure Machine Learning](/azure/machine-learning/studio/algorithm-parameters-optimize)

##  Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|Untrained model for cross validation on dataset|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Label column|any|ColumnSelection||Select the column that contains the label to use for validation|  
|Random seed|any|Integer|0|Seed value for random number generator<br /><br /> This value is optional. If not specified|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Scored results|[Data Table](data-table.md)|Results of scoring|  
|Evaluation results by fold|[Data Table](data-table.md)|Results of evaluation (by fold and entire)|  
  
##  Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0035](errors/error-0035.md)|Exception occurs if no features were provided for a given user or item.|  
|[Error 0032](errors/error-0032.md)|Exception occurs if argument is not a number.|  
|[Error 0033](errors/error-0033.md)|Exception occurs if argument is Infinity.|  
|[Error 0001](errors/error-0001.md)|Exception occurs if one or more specified columns of data set couldn't be found.|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0006](errors/error-0006.md)|Exception occurs if parameter is greater than or equal to the specified value.|  
|[Error 0008](errors/error-0008.md)|Exception occurs if parameter is not in range.|  
|[Error 0013](errors/error-0013.md)|Exception occurs if the learner that is passed to the module has an invalid type.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also
  
 [Evaluate](machine-learning-evaluate.md)   
 [Evaluate Recommender](evaluate-recommender.md)   
 [A-Z Module List](a-z-module-list.md)
