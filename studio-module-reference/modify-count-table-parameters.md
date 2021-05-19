---
title: "ML Studio (classic): Modify Count Table Parameters - Azure"
description: Learn how to use the Modify Count Table Parameters module to change the way that features are generated from a count table.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Modify Count Table Parameters

*Modifies the parameters used to create features from counts*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Modify Count Table Parameters** module in Azure Machine Learning Studio (classic), to change the way that features are generated from a count table.

In general, to create count-based features, you use [Build Counting Transform](build-counting-transform.md) to process a dataset and create a count table, and from that count table generate a new set of features. 

However, if you have already created a count table, you can use the **Modify Count Table Parameters** module to edit the definition of how the count data is processed. This lets you create a different set of count-based statistics based on the existing data, without having to re-analyze the dataset.

## How to configure Modify Count Parameters

1. Locate the transformation you want to modify, in the **Transforms** group, and add it to your experiment.

    You should have previously run an experiment that created a count transformation.

    + **To modify a saved transform**: Locate the transformation, in the **Transforms** group, and add it to your experiment.

    + **To modify a count transformation created within the same experiment**: If the transformation has not been saved, but is available as an output in the current experiment (for example, check the output of the [Build Counting Transform](build-counting-transform.md) module), you can use it directly by connecting the modules.

2. Add the **Modify Count Table Parameters** module and connect the transformation as an input.

3. In the **Properties** pane of the **Modify Count Table Parameters** module, type a value to use as the**Garbage bin threshold**.

    This value specifies the minimum number of occurrences that must be found for each feature value, in order for counts to be used.  If the frequency of the value is less than the garbage bin threshold, the value-label pair is not counted as a discrete item; instead, all items with counts lower than the threshold value are placed in a single "garbage bin".

    If you are using a small dataset and you are counting and training on the same data, a good starting value is 1.

4. For **Additional prior pseudo examples**, type a number that indicates the number of additional pseudo examples to include. You do not need to provide these examples; the pseudo examples are generated based on the prior distribution.  

5. For **Laplacian noise scale**, type a positive floating-point value that represents the scale used for introducing noise sampled from a Laplacian distribution. When you set a scale value, some acceptable level of noise is incorporated into the model, so the model is less likely to be affected by unseen values in data.

6. In **Output features include**, choose the method to use when creating count-based features for inclusion in the transformation.

    + **CountsOnly**: Create features using counts.
  
    + **LogOddsOnly**: Create features using the log of the odds ratio.
  
    + **BothCountsAndLogOdds**: Create features using both counts and log odds.
  
7. Select the **Ignore back off column** option if you want to override the `IsBackOff` flag in the output when creating features. When you select this option, count-based features are created even if the column doesn’t have significant count values.

8. Run the experiment. You can then save the output of **Modify Count Table Parameters** as a new transformation, if desired.

## Examples

For examples of how this module, see the [Azure AI Gallery](https://gallery.azure.ai/):

+ [Learning with Counts: Binary Classification](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-Classification-2): Demonstrates how to use the learning with counts modules to generate features from columns of categorical values for a binary classification model.

+ [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2):sample Demonstrates how to use the learning with counts modules for performing multiclass classification on the publicly available NYC taxi dataset. The sample uses a multiclass logistic regression learner to model this problem.

+ [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2): Demonstrates how to use the learning with counts modules for performing binary classification on the publicly available NYC taxi dataset. The sample uses a two-class logistic regression learner to model this problem.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

It is statistically safe to count and train on the same data set if you set the Laplacian noise scale parameter.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Counting transform|[ITransform interface](itransform-interface.md)|The counting transform to apply|  

## Module parameters

|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Garbage bin threshold|Float|>=0.0f|Required|10.0f|The threshold under which a column value will be featurized against the garbage bin|  
|Additional prior pseudo examples|Float|>=0.0f|Required|42.0f|The additional pseudo examples following prior distributions to be included|  
|Laplacian noise scale|Float|>=0.0f|Required|0.0f|The scale of the Laplacian distribution from which noise is sampled|  
|Output features include|OutputFeatureType||Required|BothCountsAndLogOdds|The features to output|  
|Ignore back off column|Boolean||Required|false|Whether to ignore the IsBackOff column in the output|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Modified transform|[ITransform interface](itransform-interface.md)|The modified transform|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0086](errors/error-0086.md)|Exception occurs when a counting transform is invalid.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md)   
