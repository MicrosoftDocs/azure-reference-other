---
title: "Count Featurizer (deprecated) | Microsoft Docs"
titleSuffix: ML Studio (classic) - Azure
description: Learn how to use the Count Featurizer module to create features from a previously generated count table.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Count Featurizer (deprecated)

*Creates a set of features based on a counts table*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Count Featurizer** module in Azure Machine Learning Studio (classic), to create features from a previously generated count table.

Creating features from counts is an efficient way of summarizing useful information about the distribution of data and labels in a set of training data. This method of creating features from raw data is particularly useful in large data sets with high-cardinality features.  For example, in fraud detection, count tables can be used to collect information about the user ID, product and transaction and all the possible combinations over terabytes of data.  Count tables can also be useful in improving accuracy on small data sets.

> [!WARNING]
> This module has been deprecated.

For new experiments, we recommend that you use the following modules:

- [Build Counting Transform](build-counting-transform.md)
- [Modify Count Table Parameters](modify-count-table-parameters.md)
- [Merge Count Transform](merge-count-transform.md)

If you have existing count-based features or data that you want to use in a new experiment, use the following modules to migrate an existing count table, or change the count table to a new count transformation:

- [Import Count Table](import-count-table.md)
- [Export Count Table](export-count-table.md)

## How to configure Count Featurizer

> [!IMPORTANT]
> This module has been replaced with the [Build Counting Transform](build-counting-transform.md). These instructions are provided only for customers who have existing experiments that use the older, deprecated modules.

1. In Azure Machine Learning Studio (classic), create a table of counts using the [Build Count Table (deprecated)](build-count-table-deprecated.md) module.

2. Connect the output of the [Build Count Table (deprecated)](build-count-table-deprecated.md) module to the leftmost input port of **Count Featurizer**.

3. Connect a training data set to the middle input port of **Count Featurizer**.

    It need not be the same training dataset that was used for [Build Count Table (deprecated)](build-count-table-deprecated.md), but you must select the same number of columns and they must have the same data type and values.

4. For **Select counted columns**, use the column selector to choose columns from the count table. The table must have been created using [Build Count Table (deprecated)](build-count-table-deprecated.md).  You can select a subset of the columns.

5. For **Select columns to featurize**, select the columns in the input dataset that you want to featurize. Be sure to select the same number of columns that you selected in the previous step.

    The columns must also have the same type and structure as the columns you used to build the count table.

6. For **Garbage bin threshold** type a whole number that represents the minimum number of occurrences that must be found for each value, in order for counts to be used.

    If the frequency of the value is less than the garbage bin threshold, the value-label pair is not counted.

    If you are using a small dataset and you are counting and training on the same data, a good starting value is 1.

7. For **Additional prior pseudo examples**, type the number of additional examples to include. The examples are called *pseudo examples* because they are generated based on the prior distribution.

8. For **Laplacian noise scale**, type a positive floating-point value. This number denotes the scale used when  noise is introduced based on sampling from a Laplacian distribution.

    The Laplacian noise scale parameter is provided to make it statistically safe to count and train on the same data set. In other words, by incorporating some acceptable level of noise into the model, the model becomes less susceptible to new values in data.

9. For **Output features include**, select the type of count-based features to generate:

    - **CountsOnly**: Creates features using counts.
    - **LogOddsOnly**: Creates features using the log of the odds ratio.
    - **BothCountsAndLogOdds**: Creates features using both counts and log odds.

10. Select the option, **Ignore back off column**, if you want to ignore the `IsBackOff` column in the output when creating features.

## Examples

Explore examples of count-based featurization in the [Azure AI Gallery](https://gallery.azure.ai/):

- [Flight delay prediction](https://go.microsoft.com/fwlink/?LinkId=525277): Shows how count-based featurization can be useful in a very large dataset.

- [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2): Demonstrates the use of count-based features in a multiclass prediction task.

- [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2): Uses count-based features in a binary classification task.

> [!NOTE]
> These experiments were all created using the earlier, and now deprecated, version of the [Learning with Counts](data-transformation-learning-with-counts.md) modules. When you open the experiment in Studio (classic), the experiment is automatically upgraded to use the newer modules.

## Technical notes

It is statistically safe to count and train on the same data set if you set the Laplacian noise scale parameter.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Count metadata|[Data Table](data-table.md)|The metadata of the counts.|  
|Count table|[Data Table](data-table.md)|The count table.|  
|Input dataset|[Data Table](data-table.md)|The data set to be featurized.|  

## Module parameters

|Name|Type|Range|Optional|Default|Description|  
|----------|----------|-----------|--------------|-------------|-----------------|  
|Additional prior pseudo examples|Float|>=0.0f|Required|42.0f|Provide additional pseudo examples following prior distribution, to include with the counts.|  
|Garbage bin threshold|Float|>=0.0f|Required|10.0f|Specify the threshold under which a column value will be featurized against the garbage bin.|  
|Ignore back off column|Boolean||Required|false|Indicate whether the IsBackOff column should be ignored when creating results.|  
|Laplacian noise scale|Float|>=0.0f|Required|0.0f|Specify a scale to apply when introducing noise sampled from Laplacian distribution.|  
|Output features include|OutputFeatureType||Required|BothCountsAndLogOdds|Select the features to include in the output.|  
|Select columns to featurize|ColumnSelection||Required||Select the columns to featurize. This must be a subset of the counted columns.|  
|Select counted columns|ColumnSelection||Required||Select the columns that have been used to build count table.|

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Featured data|[Data Table](data-table.md)|The featured data.|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Build Count Table (deprecated)](build-count-table-deprecated.md)
