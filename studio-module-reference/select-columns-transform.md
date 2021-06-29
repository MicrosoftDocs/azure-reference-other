---
title: "ML Studio (classic): Select Columns Transform - Azure"
description: Learn how to use the Select Columns Transform module to ensure that a predictable, consistent set of columns is always used in downstream machine learning operations.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Select Columns Transform

*Creates a transformation that selects the same subset of columns as in the given dataset*

Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

This article describes how to use the **Select Columns Transform** module in Machine Learning Studio (classic). The purpose of the **Select Columns Transform** module is to ensure that a predictable, consistent set of columns is always used in downstream machine learning operations.

This module is particularly helpful for tasks such as scoring, which require specific columns. Changes in the available columns might break the experiment or change the results.

You use the **Select Columns Transform** to create and save a set of columns. Then, use the [Apply Transformation](apply-transformation.md) module to apply those selections to new data.

## How to use Select Columns Transform

This scenario assumes that you intend to use feature selection to generate a dynamic set of columns that will be used for training a model. To ensure that column selections are the same for the scoring process, you use the **Select Columns Transform** module to capture the column selections and apply them elsewhere in the experiment.

1. Add an input dataset to your experiment in Studio (classic).

2. Add an instance of [Filter Based Feature Selection](filter-based-feature-selection.md).

3. Connect the modules and configure the feature selection module to automatically find some number of best features in the input dataset.

4. Add an instance of [Train Model](train-model.md) and use the output of [Filter Based Feature Selection](filter-based-feature-selection.md) as the input for training.

    > [!IMPORTANT]
    > Because feature importance is decided based on the values in the column, you cannot know in advance which columns might be available for input to [Train Model](train-model.md).  

5. Now, attach an instance of the **Select Columns Transform** module. 

    This generates a column selection as a transformation that can be saved or applied to other datasets. This step ensures that the columns identified by feature selection are saved for reuse by other modules.

6. Add the [Score Model](score-model.md) module. 

    **Do not connect the input dataset.**

    Instead, add the [Apply Transformation](apply-transformation.md) module, and connect the output of the feature selection transformation.

   > [!IMPORTANT]
   > You cannot expect to apply [Filter Based Feature Selection](filter-based-feature-selection.md) to the scoring dataset, and get the same results. Since feature selection is based on values, it might choose a different set of columns, which would cause the scoring operation to fail.

7. Run the experiment.

This process of saving and then applying a column selection ensures that the same data schema is available for training and scoring.

## Examples

For examples of how to use this module, see the [Azure AI Gallery](https://gallery.azure.ai):

+ [Select columns transform](https://gallery.azure.ai/Experiment/Select-columns-transform-1): A complete walkthrough that uses this module.

+ [Filter features and remove them from scoring inputs](https://gallery.azure.ai/Experiment/Filter-Features-And-Remove-Them-From-Scoring-Inputs-1): Save this experiment to your workspace to see how the module is used in a complete experimental workflow.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset with desired columns|[Data Table](data-table.md)|Dataset containing desired set of columns|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Columns selection transformation|[ITransform interface](itransform-interface.md)|Transformation that selects the same subset of columns as in the given dataset.|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

## See also

[Manipulation](data-transformation-manipulation.md)   
 [Select Columns in Dataset](select-columns-in-dataset.md)   
