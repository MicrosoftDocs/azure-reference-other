---
title: "ML Studio (classic): PCA-Based Anomaly Detection - Azure"
description: Learn how to use the PCA-Based Anomaly Detection module to create an anomaly detection model based on Principal Component Analysis (PCA).
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# PCA-Based Anomaly Detection

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates an anomaly detection model using Principal Component Analysis*

Category: [Anomaly Detection](anomaly-detection.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **PCA-Based Anomaly Detection** module in Machine Learning Studio (classic), to create an anomaly detection model based on Principal Component Analysis (PCA).

This module helps you build a model in scenarios where it is easy to obtain training data from one class, such as valid transactions, but difficult to obtain sufficient samples of the targeted anomalies. 

For example, to detect fraudulent transactions, very often you don't have enough examples of fraud to train on, but have many examples of good transactions. The **PCA-Based Anomaly Detection** module solves the problem by analyzing available features to determine what constitutes a "normal" class, and applying distance metrics to identify cases that represent anomalies. This let you train a model using existing imbalanced data.

## More about Principal Component Analysis

*Principal Component Analysis*, which is frequently abbreviated to PCA, is an established technique in machine learning. PCA is frequently used in exploratory data analysis because it reveals the inner structure of the data and explains the variance in the data.

PCA works by analyzing data that contains multiple variables. It looks for correlations among the variables and determines the combination of values that best captures differences in outcomes. These combined feature values are used to create a more compact feature space called the *principal components*.

For anomaly detection, each new input is analyzed, and the anomaly detection algorithm computes its projection on the eigenvectors, together with a normalized reconstruction error. The normalized error is used as the anomaly score. The higher the error, the more anomalous the instance is.

For additional information about how PCA works, and about the implementation for anomaly detection, see these papers:

- [A randomized algorithm for principal component analysis](https://arxiv.org/abs/0809.2274). Rokhlin, Szlan and Tygert

- [Finding Structure with Randomness: Probabilistic Algorithms for Constructing Approximate Matrix Decompositions](http://users.cms.caltech.edu/~jtropp/papers/HMT11-Finding-Structure-SIREV.pdf) (PDF download). Halko, Martinsson and Tropp.

## How to configure PCA Anomaly Detection

1. Add the **PCA-Based Anomaly Detection** module to your experiment in Studio (classic). You can find this module under **Machine Learning**, **Initialize Model**, in the **Anomaly Detection** category.

2. In the **Properties** pane for the **PCA-Based Anomaly Detection** module, click the **Training mode** option, and indicate whether you want to train the model using a specific set of parameters, or use a parameter sweep to find the best parameters.

    - **Single Parameter**:  Select this option if you know how you want to configure the model, and provide a specific set of values as arguments.
  
    - **Parameter Range**:  Select this option if you are not sure of the best parameters and want to use a parameter sweep, using the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module. The trainer iterates over a range of settings you specify, and determines the combination of settings that produces the optimal results.

3. **Number of components to use in PCA**, **Range for number of PCA components**: Specify the number of output features, or components, that you want to output.

    The decision of how many components to include is an important part of experiment design using PCA. General guidance is that you should not include the same number of PCA components as there are variables. Instead, you should start with some smaller number of components and increase them until some criteria is met.

    If you are unsure of what the optimum value might be, we recommend that you train the anomaly detection model using the **Parameter Range** option.

    The best results are obtained when the number of output components is **less than** the number of feature columns available in the dataset.

4. Specify the amount of oversampling to perform during randomized PCA training. In anomaly detection problems, imbalanced data makes it difficult to apply standard PCA techniques. By specifying some amount of oversampling, you can increase the number of target instances.

    If you specify 1, no oversampling is performed. If you specify any value higher than 1, additional samples are generated to use in training the model.

    There are two options, depending on whether you are using a parameter sweep or not:

    - **Oversampling parameter for randomized PCA**: Type a single whole number that represents the ratio of oversampling of the minority class over the normal class. (Available when using the **Single parameter** training method.)
    - **Range for the oversampling parameter used in randomized PCA**: Type a series of numbers to try, or use the Range Builder to select values using a slider. (Available only when using the **Parameter range** training method.)

    > [!NOTE]
    > You cannot view the oversampled data set. For additional details of how oversampling is used with PCA, see [Technical notes](#bkmk_Notes).

5. **Enable input feature mean normalization**:   Select this option to normalize all input features to a mean of zero. Normalization or scaling to zero is generally recommended for PCA, because the goal of PCA is to maximize variance among variables.

     This option is selected by default. Deselect this option if values have already been normalized using a different method or scale.

6. Connect a tagged training dataset, and one of the  training modules:

    - If you set the **Create trainer mode** option to **Single Parameter**, use the [Train Anomaly Detection Model](train-anomaly-detection-model.md) module.
    -  If you set the **Create trainer mode** option to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.

    > [!NOTE]
    > If you pass a parameter range to [Train Anomaly Detection Model](train-anomaly-detection-model.md), it uses only the first value in the parameter range list.
    > 
    > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and using the default values for the learner.
    > 
    > If you select the **Parameter Range** option and enter a single value for any parameter, that single value is used throughout the sweep, even if other parameters change across a range of values.

7. Run the experiment, or select the module and click **Run selected**.

### Results

When training is complete, you can either save the trained model, or connect it to the [Score Model](score-model.md) module to predict anomaly scores.

To evaluate the results of an anomaly detection models requires some additional steps:

1. Ensure that a score column is available in both datasets

    If you try to evaluate an anomaly detection model and get the error, "There is no score column in scored dataset to compare", it means you are using a typical evaluation dataset that contains a label column but no probability scores. You need to choose a dataset that matches the schema output for anomaly detection models, which includes a **Scored Labels** and **Scored Probabilities** column.

2. Ensure that label columns are marked

    Sometimes the metadata associated with the label column is removed in the experiment graph. If this happens, when you use the [Evaluate Model](evaluate-model.md) module to compare the results of two anomaly detection models, you might get the error, "There is no label column in scored dataset", or "There is no label column in scored dataset to compare".

    You can avoid this error by adding the [Edit Metadata](edit-metadata.md) module before the [Evaluate Model](evaluate-model.md) module. Use the column selector to choose the class column, and in the **Fields** dropdown list, select **Label**.

3. Normalize scores from different model types

    Predictions from the PCA anomaly detection model always are in the range [0,1]. In contrast, output from the [One-Class SVM](one-class-support-vector-machine.md) module are uncalibrated scores that are possibly unbounded.

    Therefore, if you are comparing models based on different algorithms, you must always normalize scores. See the example in the Azure AI Gallery for an example of normalization among different anomaly detection models.

## Examples

For examples of how PCA is used in anomaly detection, see the [Azure AI Gallery](https://gallery.azure.ai/):

- [Anomaly detection: credit risk](https://gallery.azureml.net/Experiment/1219e87f8fb84e88a2e1b54256808bb3): Illustrates how to find outliers in data. This example uses a parameter sweep to find the optimal model. It then applies that model to new data to identify risky transactions that might represent fraud, comparing two different anomaly detection models.

## <a name="bkmk_Notes"></a>Technical notes

This algorithm uses PCA to approximate the subspace containing the normal class. The subspace is spanned by eigenvectors associated with the top eigenvalues of the data covariance matrix. For each new input, the anomaly detector first computes its projection on the eigenvectors, and then computes the normalized reconstruction error. This error is the anomaly score. The higher the error, the more anomalous the instance. For details on how the normal space is computed, see Wikipedia: [Principal Component Analysis](https://wikipedia.org/wiki/Principal_component_analysis) 

## Module parameters

|Name|Type|Range|Optional|Description|Default|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Training mode|CreateLearnerMode|List:Single Parameter&#124;Parameter Range|Required|Single Parameter|Specify learner options.<br /><br /> Use the **SingleParameter** option to manually specify all values.<br /><br /> Use the **ParameterRange** option to sweep over tunable parameters.|  
|Number of components to use in PCA|Integer||mode:Single Parameter|2|Specify the number of components to use in PCA.|  
|Oversampling parameter for randomized PCA|Integer||mode:Single Parameter|2|Specify the accuracy parameter for randomized PCA training.|  
|Enable input feature mean normalization|Logic type|List:True&#124;False|Required|False|Specify if the input data is normalized to have zero mean.|  
|Range for number of PCA components|ParameterRangeSettings|[1;100]|mode:Parameter Range|2; 4; 6; 8; 10|Specify the range for number of components to use in PCA.|  
|Range for the oversampling parameter used in randomized PCA|ParameterRangeSettings|[1;100]|mode:Parameter Range|2; 4; 6; 8; 10|Specify the range for accuracy parameter used in randomized PCA training.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained PCA-based anomaly detection model|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  
|[Error 0062](errors/error-0062.md)|Exception occurs when attempting to compare two models with different learner types.|  
|[Error 0047](errors/error-0047.md)|Exception occurs if number of feature columns in some of the datasets passed to the module is too small.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## See also

 [One-Class Support Vector Machine](one-class-support-vector-machine.md)
