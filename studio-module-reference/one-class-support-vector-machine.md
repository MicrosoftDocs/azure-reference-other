---
title: "ML Studio (classic): One-Class Support Vector Machine - Azure"
description: Learn how to use the One-Class Support Vector Model module to create an anomaly detection model.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# One-Class Support Vector Machine

*Creates a one class Support Vector Machine model for anomaly detection*

Category: [Anomaly Detection](anomaly-detection.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **One-Class Support Vector Model** module in Machine Learning Studio (classic), to create an anomaly detection model.

This module is particularly useful in scenarios where you have a lot of "normal" data and not many cases of the anomalies you are trying to detect.  For example, if you need to detect fraudulent transactions, you might not have many examples of fraud that you could use to train a typical classification model, but you might have many examples of good transactions.

You use the **One-Class Support Vector Model** module to create the model, and then train the model using the [Train Anomaly Detection Model](train-anomaly-detection-model.md). The dataset that you use for training can contain all or mostly normal cases.

You can then apply different metrics to identify potential anomalies. For example, you might use a large dataset of good transactions to identify cases that possibly represent fraudulent transactions.

### More about one-class SVM

Support vector machines (SVMs) are supervised learning models that analyze data and recognize patterns, and that can be used for both classification and regression tasks.

Typically, the SVM algorithm is given a set of training examples labeled as belonging to one of two classes. 
An SVM model is based on dividing the training sample points into separate categories by as wide a gap as possible, while penalizing training samples that fall on the wrong side of the gap. The SVM model then makes predictions by assigning points to one side of the gap or the other.

Sometimes oversampling is used to replicate the existing samples so that you can create a two-class model, but it is impossible to predict all the new patterns of fraud or system faults from limited examples. Moreover, collection of even limited examples can be expensive.

Therefore, in one-class SVM, the support vector model is trained on data that has only one class, which is the “normal” class. It infers the properties of normal cases and from these properties can predict which examples are unlike the normal examples. This is useful for anomaly detection because the scarcity of training examples is what defines anomalies: that is, typically there are very few examples of the network intrusion, fraud, or other anomalous behavior.

For more information, including links to basic research, see the [Technical notes](#bkmk_Notes) section.

> [!NOTE]
> The **One-Class Support Vector Model** module creates a kernel-SVM model, which means that it is not very scalable. If training time is limited, or you have too much data, you can use other methods for anomaly detectors, such as [PCA-Based Anomaly Detection](pca-based-anomaly-detection.md).

## How to configure One-Class SVM

1. Add the **One-Class Support Vector Model** module to your experiment in Studio (classic).  You can find the module under **Machine Learning - Initialize**, in the **Anomaly Detection** category.

2. Double-click the **One-Class Support Vector Model** module to open the **Properties** pane. 

3. For **Create trainer mode**, select an option that indicates how the model should be trained:

    - **Single Parameter**: Use this option if you know how you want to configure the model, and provide a specific set of values as arguments.
  
    - **Parameter Range**: Use this option if you are not sure of the best parameters, and want to perform a parameter sweep to find the optimal configuration.

4. **η**: Type a value that represents the upper bound on the fraction of outliers. This parameter corresponds to the nu-property described in [this paper](https://research.microsoft.com/pubs/69731/tr-99-87.pdf). The nu-property lets you control the trade-off between outliers and normal cases.

4. **ε** (epsilon): Type a value to use as the stopping tolerance. The stopping tolerance, affects the number of iterations used when optimizing the model, and depends on the stopping criterion value. When the value is exceeded, the trainer stops iterating on a solution.

5. Connect a training dataset, and one of the training modules:

    - If you set **Create trainer mode** to **Single Parameter**, use the [Train Anomaly Detection Model](train-anomaly-detection-model.md) module.
    - If you set **Create trainer mode** to **Parameter Range**, use the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module.

   > [!NOTE]
   > 
   > If you pass a parameter range to [Train Anomaly Detection Model](train-anomaly-detection-model.md), it uses only the first value in the parameter range list. 
   > 
   > If you pass a single set of parameter values to the [Tune Model Hyperparameters](tune-model-hyperparameters.md) module, when it expects a range of settings for each parameter, it ignores the values and uses the default values for the learner.
   > 
   > If you select the **Parameter Range** option and enter a single value for any parameter, that single value is used throughout the sweep, even if other parameters change across a range of values.

6. Run the experiment.

### Results

The module returns a trained anomaly detection model. You can either save the model in your workspace, or you can connect the [Score Model](score-model.md) module and use the trained model to detect possible anomalies.

If you trained the model using a parameter sweep, make a note of the optimal parameter settings to use when configuring a model for use in production.

## Examples

For examples of how this module is used in anomaly detection, see the [Azure AI Gallery](https://gallery.azure.ai/):  

- [Anomaly Detection: Credit Risk](https://gallery.azureml.net/Experiment/1219e87f8fb84e88a2e1b54256808bb3): This sample illustrates how to find outliers in data, using a parameter sweep to find the optimal model. It then applies that model to new data to identify risky transactions that might represent fraud, comparing two different anomaly detection models.

## <a name="bkmk_Notes"></a>Technical notes

Predictions from the [One-Class SVM](one-class-support-vector-machine.md) are uncalibrated scores that may be possibly unbounded. As the example in the Cortana Intelligence Gallery demonstrates, be sure to normalize scores if you are comparing models based on different algorithms.

### Research

This implementation wraps the library for support vector machines named [libsvm](https://www.csie.ntu.edu.tw/~cjlin/libsvm/).  The general theory on which `libsvm` is based, and the approach towards one-class support vector machines, is described in these papers by B. Schӧlkopf et al.

- [Estimating the Support of a High-Dimensional Distribution](https://research.microsoft.com/pubs/69731/tr-99-87.pdf)

- [New Support Vector Algorithms](https://www.stat.purdue.edu/~yuzhu/stat598m3/Papers/NewSVM.pdf)

## Module parameters
  
|Name|Type|Range|Optional|Description|Default|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Create trainer mode|Create Trainer Mode|List:Single Parameter&#124;Parameter Range|Required|Single Parameter|Specify learner options.<br /><br /> Use the **SingleParameter** option to manually specify all values.<br /><br /> Use the **ParameterRange** option to sweep over tunable parameters.|  
|nu|Float|>=double.Epsilon|mode:Single Parameter|0.1|This parameter (represented by the Greek letter nu) determines the trade-off between the fraction of outliers and the number of support vectors.|  
|epsilon|Float|>=double.Epsilon|mode:Single Parameter|0.001|Specifies the stopping tolerance.|  
|psnu|ParameterRangeSettings|[0.001;1.0]|mode:Parameter Range|0.001; 0.01; 0.1|Specifies the range for the trade-off between the fraction of outliers and the number of support vectors.|  
|psEpsilon|ParameterRangeSettings|[1e-6;1.0]|mode:Parameter Range|0.001; 0.01; 0.1|Specifies the range for stopping tolerance.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Untrained model|[ILearner interface](ilearner-interface.md)|An untrained anomaly detection model|  

## See also

 [Classification](machine-learning-initialize-model-classification.md)   
 [Train Anomaly Detection Model](train-anomaly-detection-model.md)
