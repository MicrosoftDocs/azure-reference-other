---
title: "Create R Model | Microsoft Docs"
ms.custom: ""
ms.date: 04/26/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "R"
ms.assetid: 314e34a8-b24c-4870-afe6-2649b6fc7476
caps.latest.revision: 17
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Create R Model
*Creates an R model using custom resources*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Create R Model** module to create an untrained model from R script that you provide. You can base your model on any learner that is included in an R package in the Azure Machine Learning environment.  
  
 After you create the model, you can use [Train Model](train-model.md) to train the model on a dataset, like any other learner in Azure Machine Learning. The trained model can be passed to [Score Model](score-model.md) to use the model to make predictions. The trained model can then be saved, and the scoring workflow can be published as a web service.  
  
> [!WARNING]
>  Currently it is not possible to pass the scored results of an R model to [Evaluate Model](evaluate-model.md) or [Cross-Validate Model](cross-validate-model.md). If you need to evaluate a model, you can write custom R script and run it using the [Execute R Script](execute-r-script.md) module.  
  
 In addition to using the **Create R Model** to save and re-use custom R modules, you can create your own implementation of a modeling and data management process using R, upload the files in zipped format to your workspace, and then register the package as a custom module. For more information, see [Custom R Modules](https://azure.microsoft.com/documentation/articles/machine-learning-custom-r-modules/).  
  
## How to Configure Create R Model  

To illustrate the process, this example implements a two-class Naïve Bayes classifier by using the e1070 package. However, you can use any type of learner that is included in the many R packages supported in Azure Machine Learning.  
 
> [!TIP]
> See this sample in the Cortana Intelligence Gallery. You can also copy the example to your workspace and make changes!
> 
> + [Create R Model](https://gallery.cortanaintelligence.com/Experiment/Create-R-Model-3) 
 
To get started, you must provide two user-defined scripts as inputs:  
  
-   [Training script](#bkmk_TrainingScript). The R script that you provide here is used to train the model. When you run the experiment, it is deployed to the [Train Model](train-model.md) module.   
  
-   [Scoring script](#bkmk_ScoringScript).  The R script that you provide on this input is for scoring only. when you run the experiment, it is deployed to and runs using the [Score Model](score-model.md) module.   
  
  
###  <a name="bkmk_TrainingScript"></a> Training Script  
 
The following example demonstrates the type of code you might use in the **training script**. It loads an R package, creates model using a learner from the package, and configures the feature and label columns using the predefined constants and functions provided in **Create R Model**.  
  
```  
library(e1071)   
features <- get.feature.columns(dataset)   
labels   <- as.factor(get.label.column(dataset))   
train.data <- data.frame(features, labels)   
feature.names <- get.feature.column.names(dataset)   
names(train.data) <- c(feature.names, "Class")   
model <- naiveBayes(Class ~ ., train.data)   
```  
  
**Step-by-step explanation of code**  
  
1.  The first line loads the R package, **e1071**, which contain the Naïve Bayes classifier algorithm we want to use.  
  
    ```  
    library(e1071)  
    ```  
  
     Since this is one of the packages pre-installed in the Azure Machine Learning environment, you don’t need to download or install the package.  
  
     For information about how to get the full list of supported packages, see [R Language Modules](r-language-modules.md).  
  
2.  The next three lines get the feature columns and the label column from the dataset, and combine them into a new R data frame that is named `train.data`:  
  
    ```  
    features <- get.feature.columns(dataset)   
    labels   <- as.factor(get.label.column(dataset))   
    train.data <- data.frame(features, labels)   
    ```  
  
     The predefined function, `get.label.columns()`, returns the column that is selected as the class label in the [Train Model](train-model.md) module.  
  
3.  The predefined function, `get.feature.columns()`, selects the columns that were designated as features in the metadata for dataset.  
  
    > [!WARNING]
    >  By default, all columns except the label column are considered features in Studio. If you want to select specific columns as features, use [Edit Metadata](edit-metadata.md), or select a set of columns within the R script.  
  
4.  In the fifth and sixth lines, the predefined function, `get.feature.column.names(dataset)`, is used to get feature column names from the dataset. Those names are designated as the names for columns in `train.data`, and a temporary name `Class` is created for the label column.  
  
    ```  
    feature.names <- get.feature.column.names(dataset)   
    names(train.data) <- c(feature.names, "Class")   
    ```  
  
5.  The final line of the code trains the Naïve Bayes classifier algorithm by using the labels and features in the `train.data` data frame.  
  
    ```  
    model <- naiveBayes(Class ~ ., train.data)    
    ```  
  
    > [!WARNING]
    >  The model must always be assigned to a variable called `model` in both the train and score scripts.  
  
###  <a name="bkmk_ScoringScript"></a> Scoring Script  

The following code illustrates the type of R code that you would provide for your **scoring script**. 
  
```  
library(e1071)   
probabilities <- predict(model, dataset, type="raw")[,2]   
classes <- as.factor(as.numeric(probabilities >= 0.5))   
scores <- data.frame(classes, probabilities)   
```  
  
**Step-by-step explanation of code** 
  
1.  The first line loads the package.  
  
    ```  
    library(e1071)  
    ```  
  
2.  The second line computes the predicted probabilities for the scoring dataset by using the trained model from the training script.  
  
    ```  
    probabilities <- predict(model, dataset, type="raw")[,2]   
    ```  
  
3.  The third line applies a threshold of 0.5 to probabilities when assigning the predicted class labels.  
  
    ```  
    classes <- as.factor(as.numeric(probabilities >= 0.5))   
    ```  
  
4.  The final line combines the class labels and probabilities into the output data frame, `scores`.  
  
    ```  
    scores <- data.frame(classes, probabilities)   
    ```  
  
    > [!WARNING]
    >  The output dataframe must have the name `scores`.  
  
### Publishing the R Model as a Web Service  
 After you have run the experiment by using the R model, you can publish the experiment as a web service.  
  
1.  Click **Create Scoring Experiment** in the experiment editor.  
  
     The trained R model is saved, and the training experiment graph is transformed into a scoring experiment.  
  
2.  Run the scoring experiment at least once.  
  
3.  Click **Publish Web Service**.  
  
> [!NOTE]
>  By default, the web service expects all input columns from the training data to be provided, including the label column. You can add an instance of [Select Columns in Dataset](select-columns-in-dataset.md) between the input data source and the [Score Model](score-model.md) module to exclude the label you’re trying to predict.  
  
##  <a name="Notes"></a> Technical Notes  
  
-   The **Create R Model** module supports use of CRAN R only. You cannot select another version of R, or use Microsoft R Open.  
  
-   The model is cached after the first run of the module and the module is not invoked in subsequent runs until any changes in input scripts are done. Please take this behavior into consideration if your R scripts use any of the following:  
  
    -   Functions that generate random numbers  
  
    -   Functions that generate random numbers  
  
    -   Other nondeterministic functions  
  
-   R models cannot be used with these modules: [Tune Model Hyperparameters](tune-model-hyperparameters.md), [Cross-Validate Model](cross-validate-model.md), [One-vs-All Multiclass](one-vs-all-multiclass.md) or [Ordinal Regression](ordinal-regression.md).  
  
-   R models do not automatically perform feature normalization of categorical data or handle missing values. Handling of such variables should be done within the training and scoring R scripts.  
  
## Pre-Defined Functions  
  
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
  
##  <a name="bkmk_Constants"></a> Pre-Defined Constants  
  
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
 For examples of how to use this module in machine learning experiments, see the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com):  
  
-   This experiment demonstrates how to use the **Create R Model** module to train, and score a naive bayes classification model using the breast cancer dataset. It uses the [Execute Python Script](execute-python-script.md) to calculate performance and plot the performance curve: [Create R Model](https://gallery.cortanaintelligence.com/Experiment/Create-R-Model-3)  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|*Trainer R script*|Script|An R script that takes a dataset as input and outputs an untrained model.|  
|*Scorer R script*|Script|An R script that takes a model and a dataset as input and outputs the scores specified in the script.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Model|[ILearner interface](ilearner-interface.md)|An untrained model|  
  
## See Also  
 [Execute R Script](execute-r-script.md)   
 [Module Categories and Descriptions](machine-learning-module-descriptions.md)   
 [R Language Modules](r-language-modules.md)