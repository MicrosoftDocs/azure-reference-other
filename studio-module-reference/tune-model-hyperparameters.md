---
title: "ML Studio (classic): Tune Model Hyperparameters - Azure"
description: Learn how to use the Tune Model Hyperparameters module to determine the optimum hyperparameters for a given machine learning model.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Tune Model Hyperparameters
*Performs a parameter sweep on a model to determine the optimum parameter settings*  
  
 Category: [Machine Learning / Train](machine-learning-train.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview

This article describes how to use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module in Machine Learning Studio (classic), to determine the optimum hyperparameters for a given machine learning model. The module builds and tests multiple models, using different combinations of settings, and compares metrics over all models to get the combination of settings. 

The terms *parameter* and *hyperparameter* can be confusing. The model's *parameters* are what you set in the properties pane. Basically, this module performs a *parameter sweep* over the specified parameter settings, and learns an optimal set of _hyperparameters_, which might be different for each specific decision tree, dataset, or regression method. The process of finding the optimal configuration is sometimes called *tuning*. 

The module support two methods for finding the optimum settings for a model:  
  
-   **Integrated train and tune**: You configure a set of parameters to use, and then let the  module iterate over multiple combinations, measuring accuracy until it finds a "best" model. With most learner modules, you can choose which parameters should be changed during the training process, and which should remain fixed.

    Depending on how long you want the tuning process to run, you might decide to exhaustively test all combinations, or you could shorten the process by establishing a grid of parameter combinations and testing a randomized subset of the parameter grid.
  
-   **Cross validation with tuning**:  With this option, you divide your data into some number of folds and then build and test models on each fold. This method provides the best accuracy and can help find problems with the dataset; however, it takes longer to train.  
  
 Both methods generate a trained model that you can save for re-use.  

### Related tasks

+ If you are building a clustering model, use [Sweep Clustering](sweep-clustering.md) to automatically determine the optimum number of clusters and other parameters. 

+ Before tuning, apply feature selection to determine the columns or variables that have the highest information value. For more information, see [Feature Selection](feature-selection-modules.md).

## How to configure Tune Model Hyperparameters  

Generally, learning the optimal hyperparameters for a given machine learning model requires considerable experimentation. This module supports both the initial tuning process, and cross-validation to test model accuracy:

+ [Find optimal model parameters using a parameter sweep](#bkmk_sweep)

+ [Perform cross-validation during a parameter sweep](#bkmk_crossSweep)

### <a name="bkmk_sweep"></a> Train a model using a parameter sweep  

This section describes how to perform a basic parameter sweep, which trains a model by using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.
  
1.  Add the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to your experiment in Studio (classic).

2.  Connect an untrained model (a model in the [iLearner](ilearner-interface.md) format) to the leftmost input. 

3. Set the **Create trainer mode** option to **Parameter Range** and use the **Range Builder** to specify a range of values to use in the parameter sweep.  

    Almost all the [classification](machine-learning-initialize-model-classification.md) and [regression](machine-learning-initialize-model-regression.md) modules support an integrated parameter sweep. For those learners that do not support configuring a parameter range, only the available parameter values can be tested.

    You can manually set the value for one or more parameters, and then sweep over the remaining parameters. This might save some time.
  
4.  Add the dataset you want to use for training and connect it to the middle input of [Tune Model Hyperparameters](tune-model-hyperparameters.md).  
  
    Optionally, if you have a tagged dataset, you can connect it to the rightmost input port (**Optional validation dataset**). This lets you measure accuracy while training and tuning.

5.  In the **Properties** pane of [Tune Model Hyperparameters](tune-model-hyperparameters.md), choose a value for **Parameter sweeping mode**. This option controls how the parameters are selected.

    - **Entire grid**: When you select this option, the module loops over a grid predefined by the system, to try different combinations and identify the best learner. This option is useful for cases where you don't know what the best parameter settings might be and want to try all possible combination of values.

    You can also reduce the size of the grid and run a **random grid** sweep. Research has shown that this method yields the same results, but is more efficient computationally.
  
    - **Random sweep**: When you select this option, the module will randomly select parameter values over a system-defined range. You must specify the maximum number of runs that you want the module to execute. This option is useful for cases where you want to increase model performance using the metrics of your choice but still conserve computing resources.

6.  For **Label column**, launch the column selector to choose a single label column.
  
7.  Choose a single metric to use when **ranking** the models.
  
    When you run a parameter sweep, all applicable metrics for the model type are calculated and are returned in the **Sweep results** report. Separate metrics are used for regression and classification models.
    
    However, the metric you choose determines how the models are ranked. Only the top model, as ranked by the chosen metric, is output as a trained model to use for scoring.

8.  For **Random seed**, type a number to use when initializing the parameter sweep. 

    If you are training a model that supports an integrated parameter sweep, you can also set a range of seed values to use and iterate over the random seeds as well. This can be useful for avoiding bias introduced by seed selection.

9. Run the experiment.

### Results of hyperparameter tuning

When training is complete:

+ To view a set of accuracy metrics for the best model, right-click the module, select **Sweep results**, and then select **Visualize**.

    All accuracy metrics applicable to the model type are output, but the metric that you selected for ranking determines which model is considered "best". Metrics are generated only for the top-ranked model. 

+ To view the settings derived for the "best" model, right-click the module, select **Trained best model**, and then click **Visualize**. The report includes parameter settings and feature weights for the input columns.

+ To use the model for scoring in other experiments, without having to repeat the tuning process, right-click the model output and select **Save as Trained Model**. 

### <a name="bkmk_crossSweep"></a> Perform cross-validation with a parameter sweep

This section describes how to combine a parameter sweep with cross-validation. This process takes longer, but you can specify the number of folds, and you get the maximum amount of information about your dataset and the possible models.
  
1.  Add the [Partition and Sample](partition-and-sample.md) module to your experiment, and connect the training data.  

2. Choose the **Assign to Folds** option and specify some number of folds to divide the data into. If you don't specify a number, by default 10 folds are used. Rows are apportioned randomly into these folds, without replacement.

3. To balance the sampling on some column, set the **Stratified split** to **TRUE**, and then select the _strata column_. For example, if you have an imbalanced dataset, you might want to divide the dataset such that each fold gets the same number of minority cases. 

4.  Add the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module to your experiment.  

5.  Connect one of the machine learning modules in [this category](machine-learning-initialize-model.md) to the left-hand input of [Tune Model Hyperparameters](tune-model-hyperparameters.md). 

6. In the **Properties** pane for the learner, set the **Create trainer mode** option to **Parameter Range** and use the **Range Builder** to specify a range of values to use in the parameter sweep.  

    You don’t need to specify a range for all values. You can manually set the value for some parameters, and then sweep over the remaining parameters. This might save some time. 

    For a list of learners that don't support this option, see the [Technical Notes](#bkmk_Notes) section.

7.  Connect the output of [Partition and Sample](partition-and-sample.md) to the labeled **Training dataset** input of [Tune Model Hyperparameters](tune-model-hyperparameters.md).  

8. Optionally, you can connect a validation dataset to the rightmost input of [Tune Model Hyperparameters](tune-model-hyperparameters.md). For cross-validation, you need only a training dataset.

9.  In the **Properties** pane of [Tune Model Hyperparameters](tune-model-hyperparameters.md), indicate whether you want to perform a random sweep or a grid sweep. A grid sweep is exhaustive, but more time-consuming. A random parameter search can get good results without taking quite so much time.

    **Maximum number of runs on random sweep**: If you choose a random sweep, you can specify how many times the model should be trained, using a random combination of parameter values.
  
    **Maximum number of runs on random grid**: This option also controls the number of iterations over a random sampling of parameter values, but the values are not generated randomly from the specified range; instead, a matrix is created of all possible combinations of parameter values and a random sampling is taken over the matrix. This method is more efficient and less prone to regional oversampling or undersampling.

    > [!TIP]
    > For a more in-depth discussion of these options, see the [Technical notes](#bkmk_Notes) section.

9. Choose a single label column.

10. Choose a **single** metric to use in ranking the model. Many metrics are computed, so select the most important one to use in ordering the results.

11. For **Random seed**, type a number to use when initializing the parameter sweep.  

    If you are training a model that supports an integrated parameter sweep, you can also set a range of seed values to use and iterate over the random seeds as well. This is optional, but can be useful for avoiding bias introduced by seed selection.

12. Add the [Cross-Validate Model](cross-validate-model.md) module. Connect the output of [Partition and Sample](partition-and-sample.md) to the **Dataset** input, and connect the output of [Tune Model Hyperparameters](tune-model-hyperparameters.md) to the **Untrained model** input.

13.  Run the experiment.

### Results of cross-validation

When cross-validation is complete:

+ To view the evaluation results, right-click the module, select **Evaluation results by fold**, and then select **Visualize**. 

    The accuracy metrics are calculated from the cross-validation pass, and may vary slightly depending on how many folds you selected. 

+ To see how the dataset was divided, and how the "best" model would score each row in the dataset, right-click the module, select **Scored results**, and then select **Visualize**.

+ If you save this dataset for later re-use, the fold assignments are preserved. For example, the saved datsaet might look like this:

    |Fold assignments| Class| Age(1st feature column)|
    |----|----|----|
    |2|0|35|  
    |1|1|17|
    |3|0|62|

+ To get the parameter settings for the "best" model, right-click [Tune Model Hyperparameters](tune-model-hyperparameters.md)

## Examples

For examples of how this module is used, see the [Azure AI Gallery](https://gallery.azure.ai):  

- [Prediction of student performance](https://gallery.azure.ai/Experiment/da44bcd5dc2d4e059ebbaf94527d3d5b?r=legacy): Uses the [Two-Class Boosted Decision Tree](two-class-boosted-decision-tree.md) algorithm with different parameters to generate a model with the best possible root mean squared error (RMSE).

- [Learning with Counts: Binary Classification](https://gallery.azure.ai/Experiment/47deb75fc7bb428194e9d0d5713350c8?r=legacy): Generates a compact set of features using count-based learning, and then applies a parameter sweep to find the best model parameters.

- [Binary Classification: Network intrusion detection](https://gallery.azure.ai/Experiment/e7fb30de726e4e02b034233ec6c34ce4?r=legacy): Uses [Tune Model Hyperparameters](tune-model-hyperparameters.md) in cross-validation mode, with a custom split into five folds, to find the best hyperparameters for a [Two-Class Logistic Regression](two-class-logistic-regression.md) model.

## <a name="bkmk_Notes"></a>Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### How a parameter sweep works

This section describes how  parameter sweep works in general, and how the options in this module interact.

When you set up a parameter sweep, you define the scope of your search, to use either a finite number of parameters selected randomly, or an exhaustive search over a parameter space you define.

+ **Random sweep**: This option trains a model using a set number of iterations. 
 
     You specify a range of values to iterate over, and the module uses a randomly chosen subset of those values.  Values are chosen with replacement, meaning that numbers previously chosen at random are not removed from the pool of available numbers. Thus, the chance of any value being selected remains the same across all passes.  
  
+ **Grid sweep**: This option creates a matrix, or grid, that includes every combination of the parameters in the value range you specify. When you start tuning with this module, multiple models are trained using combinations of these parameters.  
  
+ **Entire grid**: The option to use the entire grid means just that: each and every combination is tested. This option can be considered the most thorough, but requires the most time. 

+ **Random grid**: If you select this option, the matrix of all combinations is calculated and values are sampled from the matrix, over the number of iterations you specified.

    Recent research has shown that random sweeps can perform better than grid sweeps.  

### Controlling the length and complexity of training

Iterating over many combinations of settings can be time-consuming, so the module provides several ways to constrain the process:

+ Limit the number of iterations used to test a model
+ Limit the parameter space
+ Limit both the numer of iterations and the parameter space

We recommend that you experiment with the settings to determine the most efficient method of training on a particular dataset and model.

### Choosing an evaluation metric

A report containing the accuracy for each model is presented at the end so that you can review the metric results. A uniform set of metrics is used for all classification models, and a different set of metrics is used for regression models. However, during training, you must choose a **single** metric to use in ranking the models that are generated during the tuning process. You might find that the best metric varies, depending on your business problem, and the cost of false positives and false negatives.

For more information, see [How to evaluate model performance in Machine Learning](/azure/machine-learning/classic/evaluate-model-performance)


#### Metrics used for classification

-   **Accuracy** The proportion of true results to total cases.  
  
-   **Precision** The proportion of true results to positive results.  
  
-   **Recall** The fraction of all correct results over all results.  
  
-   **F-score** A measure that balances precision and recall.  
  
-   **AUC** A value that represents the area under the curve when false positives are plotted on the x-axis and true positives are plotted on the y-axis.  
  
-   **Average Log Loss** The difference between two probability distributions: the true one, and the one in the model.  
  
-   **Train Log Loss** The improvement provided by the model over a random prediction.  
  
#### Metrics used for regression

-   **Mean absolute error** Averages all the error in the model, where error means the distance of the predicted value from the true value. Often abbreviated as **MAE**.  
  
-   **Root of mean squared error** Measures the average of the squares of the errors, and then takes the root of that value. Often abbreviated as **RMSE**  
  
-   **Relative absolute error** Represents the error as a percentage of the true value.  
  
-   **Relative squared error** Normalizes the total squared error it by dividing by the total squared error of the predicted values.  
  
-   **Coefficient of determination** A single number that indicates how well data fits a model. A value of 1 means that the model exactly matches the data; a value of 0 means that the data is random or otherwise cannot be fit to the model. Often referred to as **r<sup>2</sup>**, **R<sup>2</sup>**, or **r-squared**.  

### Modules that do not support a parameter sweep

Almost all learners in Machine Learning support cross-validation with an integrated parameter sweep, which lets you choose the parameters to experiment with. If the learner doesn't support setting a range of values, you can still use it in cross-validation. In this case, some range of allowed values is selected for the sweep. 

The following learners do not support setting a range of values to use in a parameter sweep:

+ [Two-Class Bayes Point Machine](two-class-bayes-point-machine.md)
+ [Bayesian Linear Regression](bayesian-linear-regression.md)

##  Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|Untrained model for parameter sweep|  
|Training dataset|[Data Table](data-table.md)|Input dataset for training|  
|Validation dataset|[Data Table](data-table.md)|Input dataset for validation (for Train/Test validation mode). This input is optional.|  
  
##  Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Specify parameter sweeping mode|List|Sweep Methods|Random sweep|Sweep entire grid on parameter space, or sweep with using a limited number of sample runs|  
|Maximum number of runs on random sweep|[1;10000]|Integer|5|Execute maximum number of runs using random sweep|  
|Random seed|any|Integer|0|Provide a value to seed the random number generator|  
|Label column|any|ColumnSelection||Label column|  
|Metric for measuring performance for classification|List|Binary Classification Metric Type|Accuracy|Select the metric used for evaluating classification models|  
|Metric for measuring performance for regression|List|RegressionMetric Type|Mean absolute error|Select the metric used for evaluating regression models|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Sweep results|[Data Table](data-table.md)|Results metric for parameter sweep runs|  
|Trained best model|[ILearner interface](ilearner-interface.md)|Model with best performance on the training dataset|  
  
## See also  
 [A-Z Module List](a-z-module-list.md)   
 [Train](machine-learning-train.md)   
 [Cross-Validate Model](cross-validate-model.md)
