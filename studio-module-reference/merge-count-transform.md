---
title: "ML Studio (classic): Merge Count Transform - Azure"
description: Learn how to use the Merge Count Transform module to combine two sets of count-based features.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Merge Count Transform

*Creates a set of features based on a counts table*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Merge Count Transform** module in Machine Learning Studio (classic), to combine two sets of count-based features. By merging two sets of related counts and features, you can potentially improve the coverage and distribution of the features.

Learning from counts is particularly useful in large data sets with high-cardinality features.  The ability to combine multiple datasets into count-based feature sets without having to reprocess the datasets makes it easier to gather statistics on very large datasets and apply them to new datasets. For example, count tables can be used to collect information over terabytes of data. You can re-use those statistics to improve the accuracy of predictive models on small data sets.

To merge two sets of count-based features, the features must have been created using tables that have the same schema: that is, both sets must use the same columns, and have the same names and data types.

## How to configure Merge Count Transform

1. To use **Merge Count Transform**, you must have created at least one count-based transformation, and that transformation must be present in your workspace. If you saved a count-based transformation from a different experiment, look in the **Transforms** group. If you created the transformation in the current experiment, connect the outputs of the following modules:

    - [Build Counting Transform](build-counting-transform.md). Creates a new count-based transformation from source data.

    - [Modify Count Table Parameters](modify-count-table-parameters.md). Takes an existing count transformation as an input and outputs an updated transformation.

    - [Import Count Table](import-count-table.md). This module supports backward compatibility with older experiments that used count-based learning. If you used [Import Count Table](import-count-table.md) to analyze the distribution of values in a dataset, and then converted the values to features using the deprecated Count Featurizer module, use [Import Count Table](import-count-table.md) to convert the results to a transformation.

2. Add the **Merge Count Transform** module to the experiment, and connect a transformation to each input.

    > [!TIP]
    > The second transformation is an optional input – you can connect the same transformation twice, or connect nothing on the second input port.

3. If you do not want the second dataset to be weighted equally with the first, specify a value for **Decay factor**. The value that you type indicates how the set of features from the second transformation should be weighted.

    For example, the default value of 1 weights both sets of features equally. A value of .5 means that the features in the second set would have half the weight of those in the first set.

4. Optionally, add an instance of the [Apply Transformation](apply-transformation.md) module, and apply the transformation to a dataset.

## Examples

For examples of how this module is used, see the [Azure AI Gallery](https://gallery.azure.ai/):

- [Learning with Counts: Binary Classification](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-Classification-2): Demonstrates how to use the learning with counts modules to generate features from columns of categorical values for a binary classification model.

- [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2): Demonstrates how to use the learning with counts modules for performing multiclass classification on the publicly available NYC taxi dataset. The sample uses a multiclass logistic regression learner to model this problem.

- [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2): Demonstrates how to use the learning with counts modules for performing binary classification on the publicly available NYC taxi dataset. The sample uses a two-class logistic regression learner to model the problem.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Previous counting transform|[ITransform interface](itransform-interface.md)|The counting transform to edit|  
|New counting transform|[ITransform interface](itransform-interface.md)|The counting transform to add (optional)|  

## Module parameters

|Name|Type|Range|Optional|Description|Default|  
|----------|----------|-----------|--------------|-----------------|-------------|  
|Decay factor|Float||Required|1.0f|The decay factor to be multiplied to the counting transform at the right input port|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Merged counting transform|[ITransform interface](itransform-interface.md)|The merged transform|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0086](errors/error-0086.md)|Exception occurs when a counting transform is invalid.|  

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md)   
