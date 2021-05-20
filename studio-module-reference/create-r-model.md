---
title: "ML Studio (classic): Create R Model - Azure"
description: Learn how to use the Create R Model module to create an untrained model from an R script. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
dev_langs: 
  - "R"


author: xiaoharper
ms.author: amlstudiodocs

---
# Create R Model

*Creates an R model using custom resources*

Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Create R Model** module in Azure Machine Learning Studio (classic), to create an untrained model from an R script. 

You can base the model on any learner that is included in an R package in the Azure Machine Learning environment. 

After you create the model, you can use [Train Model](train-model.md) to train the model on a dataset, like any other learner in Azure Machine Learning. The trained model can be passed to [Score Model](score-model.md) to use the model to make predictions. The trained model can then be saved, and the scoring workflow can be published as a web service.

> [!WARNING]
> Currently it is not possible to pass the scored results of an R model to [Evaluate Model](evaluate-model.md) or [Cross-Validate Model](cross-validate-model.md). If you need to evaluate a model, you can write custom R script and run it using the [Execute R Script](execute-r-script.md) module.  

In addition to using the **Create R Model** to save and re-use custom R modules, you can create your own implementation of a modeling and data management process using R, upload the files in zipped format to your workspace, and then register the package as a custom module. For more information, see [Custom R Modules](/azure/machine-learning/classic/custom-r-modules).  

## How to configure Create R Model

Use of this module requires intermediate or expert knowledge of R. The module supports use of any learner that is included in the R packages already installed in Azure Machine Learning.

This sample from the [Azure AI Gallery](https://gallery.azure.ai) implements a two-class Naïve Bayes classifier by using the popular `e1070` package: + [Create R Model](https://gallery.azure.ai/Experiment/Create-R-Model-3). We recommend that you copy the example to your workspace and follow along.

1. Add these modules to your experiment: **Create R Model**, [Train Model](train-model.md), [Score Model](score-model.md).

2. In the **Properties** pane of **Create R Model**, provide these scripts:

    - [Trainer R script](#bkmk_TrainingScript): The R script that you provide here is used to train the model. When you run the experiment, it is deployed to the [Train Model](train-model.md) module.

    - [Scorer R script](#bkmk_ScoringScript): The R script that you provide on this input is for scoring only. when you run the experiment, it is deployed to the [Score Model](score-model.md) module.

3. The sample experiment also include the [Execute Python Script](execute-python-script.md) module, which is used to plot graphs for model evaluation. This module is optional when publishing to a web service but useful when developing the experiment.

    + To view the charts from the Python script, right-click the Python module, select **Python Device**, and select **Visualize**.
    + To view just the model metrics, right-click the Python module, select **Python Dataset**, and select **Visualize**.

    For the code in the optional Python module, see [Python module for model evaluation](#pyscript).

### <a name="bkmk_TrainingScript"></a> Training script

The following example demonstrates the type of code you might use in **Trainer R script**. 

This script loads an R package, creates model using a learner from the package, and configures the feature and label columns using the predefined constants and functions provided in **Create R Model**.

```R
library(e1071)
features <- get.feature.columns(dataset)
labels   <- as.factor(get.label.column(dataset))
train.data <- data.frame(features, labels)
feature.names <- get.feature.column.names(dataset)
names(train.data) <- c(feature.names, "Class")
model <- naiveBayes(Class ~ ., train.data)
```

- The first line loads the R package, **e1071**, which contain the Naïve Bayes classifier algorithm we want to use. Since this is one of the packages pre-installed in the Azure Machine Learning environment, you don’t need to download or install the package.  

- The next lines get the feature columns and the label column from the dataset, and combine them into a new R data frame that is named `train.data`:

    ```R
    features <- get.feature.columns(dataset)   
    labels <- as.factor(get.label.column(dataset))   
    train.data <- data.frame(features, labels)
    feature.names <- get.feature.column.names(dataset)
    ```

- Note use of these predefined functions:

    - `get.label.columns()` returns the column that is selected as the class label in the [Train Model](train-model.md) module.
    - `get.feature.columns()`selects the columns that were designated as features in the dataset.

        By default, all columns except the label column are considered features in Studio (classic). Therefore, to mark specific columns as features, use [Edit Metadata](edit-metadata.md), or select a set of columns within the R script.
    - `get.feature.column.names(dataset)` gets feature column names from the dataset. 

- The names from the combined dataset are designated as the names for columns in `train.data`, and a temporary name `Class` is created for the label column.

    ```R
    names(train.data) <- c(feature.names, "Class")
    ```

- The final line of the code defines the Naïve Bayes classifier algorithm as a function of the variables (features) and outcomes (labels) in the `train.data` data frame.

    ```R
    model <- naiveBayes(Class ~ ., train.data)
    ```

- Throughout the model creation, training, and scoring scripts, you must use the variable name `model`.

###  <a name="bkmk_ScoringScript"></a> Scoring script

The following code illustrates the type of R code that you would provide in **Scorer R script**. 

```R
library(e1071)
probabilities <- predict(model, dataset, type="raw")[,2]
classes <- as.factor(as.numeric(probabilities >= 0.5))
scores <- data.frame(classes, probabilities)
```

- The first line loads the package.

- The second line computes the predicted probabilities for the scoring dataset by using the trained model from the training script, designated by the required variable name, `model`.

- The third line applies a threshold of 0.5 to probabilities when assigning the predicted class labels.

- The final line combines the class labels and probabilities into the output data frame, `scores`.

- The data frame that gets passed to the [Score Model](score-model.md) module must have the name `scores`.

## <a name="pyscript"></a> Optional Python evaluation script

The sample experiment in the Azure AI Gallery includes the following Python script, which is used to generate metrics and charts for model evaluation.

```Python
def azureml_main(dataframe):
    import matplotlib
    matplotlib.use("agg")
    
    from sklearn.metrics import accuracy_score, precision_score, recall_score, roc_auc_score, roc_curve
    import pandas as pd
    import numpy as np
    import matplotlib.pyplot as plt
    
    scores = dataframe.ix[:, ("Class", "classes", "probabilities")]
    ytrue = scores["Class"]
    ypred = np.array([float(val) for val in scores["classes"]])    
    probabilities = scores["probabilities"]
    
    accuracy, precision, recall, auc = \
    accuracy_score(ytrue, ypred),\
    precision_score(ytrue, ypred),\
    recall_score(ytrue, ypred),\
    roc_auc_score(ytrue, probabilities)
    
    metrics = pd.DataFrame();
    metrics["Metric"] = ["Accuracy", "Precision", "Recall", "AUC"];
    metrics["Value"] = [accuracy, precision, recall, auc]

# Plot ROC Curve
    fpr, tpr, thresholds = roc_curve(ytrue, probabilities)
    fig = plt.figure()
    axis = fig.gca()
    axis.plot(fpr, tpr, linewidth=8)
    axis.grid("on")
    axis.set_xlabel("False positive rate")
    axis.set_ylabel("True positive rate")
    axis.set_title("ROC Curve")
    fig.savefig("roc.png")

    return metrics,
```

## Publish the custom R model workflow as a web service

After you have run the experiment, you can publish the complete experiment as a web service.

For updated instructions on how to create a web service from a Studio (classic) experiment, see [Walkthrough Step 5: Deploy the Azure Machine Learning web service](/azure/machine-learning/studio/walkthrough-5-publish-web-service)

By default, the web service expects all input columns from the training data to be provided, including the label column. You can add an instance of [Select Columns in Dataset](select-columns-in-dataset.md) between the input data source and the [Score Model](score-model.md) module to exclude the label you’re trying to predict.

## Technical notes

- The **Create R Model** module supports use of CRAN R only. You cannot select another version of R, or use Microsoft R Open.

- The model is cached after the first run of the module and the module is not invoked in subsequent runs until any changes in input scripts are done. Please take this behavior into consideration if your R scripts use any of the following:

    - Functions that generate random numbers
    - Functions that generate random numbers
    - Other nondeterministic functions

- Custom R models created with this module cannot be used with these modules:

    - [Tune Model Hyperparameters](tune-model-hyperparameters.md)
    - [Cross-Validate Model](cross-validate-model.md)
    - [One-vs-All Multiclass](one-vs-all-multiclass.md)
    - [Ordinal Regression](ordinal-regression.md)

- R models do not automatically perform feature normalization of categorical data or handle missing values. Handling of such variables should be done within the training and scoring R scripts.

## Table of pre-defined functions

|Usage|Description|  
|-----------|-----------------|  
|`get.feature.columns(dataset)`|Gets all feature columns.|  
|`get.label.column(dataset, label.type=TrueLabelType)`|Gets the label column, given the type.<br /><br /> See the [Constants](#bkmk_Constants) section for a list of the available types.|  
|`get.label.column.names(dataset)`|Gets the names of all label columns.|  
|`get.label.column.name(dataset, label.type=TrueLabelType)`|Gets the name of the label column, given the type.<br /><br /> See the [Constants](#bkmk_Constants) section for a list of the available types.|  
|`get.label.column.types(dataset)`|Gets the types of all label columns.|  
|`get.feature.column.names(dataset)`|Gets the names of all feature columns.|  
|`dataset < - set.score.column(dataset, score.type, column.name)`|Sets the score column, given a type.<br /><br /> See the [Constants](#bkmk_Constants) section for a list of the available types.|  
|`dataset < - set.feature.channel(dataset, channel.name, column.names)`|Sets the feature channel, given a name.<br /><br /> See the [Constants](#bkmk_Constants) section for a list of the available names.|  

## <a name="bkmk_Constants"></a> Table of pre-defined constants

|Constant|Description|  
|--------------|-----------------|  
|TrueLabelType|True label column type|  
|ScoredLabelType|Scored label column type|  
|RawScoreType|Raw score column type|  
|CalibratedScoreType|Calibrated score column type|  
|ScoredProbabilitiesMulticlassColumnTypePattern|The pattern to prepare scored probabilities column type for multiclass classifier|  
|BayesianLinearRegressionScoresFeatureChannel|The name of the feature channel with Bayesian linear regression scores|  
|BinaryClassificationScoresFeatureChannel|The name of the feature channel with binary classification scores|  
|MulticlassClassificationScoresFeatureChannel|The name of the feature channel with multiclass classification scores|  
|OrdinalRegressionScoresFeatureChannel|The name of the feature channel with ordinal regression scores|  
|RegressionScoresFeatureChannel|The name of the feature channel with regression scores|  

## Examples

For additional examples of how to use this module in machine learning experiments, see the [Azure AI Gallery](https://gallery.azure.ai).

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|*Trainer R script*|Script|An R script that takes a dataset as input and outputs an untrained model.|  
|*Scorer R script*|Script|An R script that takes a model and a dataset as input and outputs the scores specified in the script.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Model|[ILearner interface](ilearner-interface.md)|An untrained model|  

## See also

 [Execute R Script](execute-r-script.md)   
 [R Language Modules](r-language-modules.md)
