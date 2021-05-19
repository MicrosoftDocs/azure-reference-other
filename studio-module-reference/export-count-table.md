---
title: "ML Studio (classic): Export Count Table - Azure"
description: Learn how to use the Export Count Table to separate the count-based features produced by deprecated Build Count Table and  Count Featurizer modules.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Export Count Table

*Exports the count table from a saved transformation for use with new data*

Category: [Learning with Counts](data-transformation-learning-with-counts.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Export Count Table** module in Azure Machine Learning Studio (classic). The **Export Count Table** module is provided for backward compatibility with experiments that use the deprecated Build Count Table and deprecated Count Featurizer modules.

When you use the new [Build Counting Transform](build-counting-transform.md) module to create count-based features, the module outputs both a featurized dataset and a *transform* that creates features from counts. By using the **Export Count Table** module, you can separate the count-based features output by this newer module into **count metadata** and a **count table**. These output formats were used by earlier, now deprecated modules:

For general information about count tables and how they are used to create features, see [Learning with Counts](data-transformation-learning-with-counts.md).

> For all new experiments, we recommend that you use the following modules:
> 
> + [Build Counting Transform](build-counting-transform.md)
> + [Modify Count Table Parameters](modify-count-table-parameters.md)
> + [Merge Count Transform](merge-count-transform.md)

## How to configure Export Count Table

1. In Azure Machine Learning Studio (classic), open the experiment where you want to use the imported count table.

2. Locate the saved count transformation, and add it to the experiment.

3. Connect the output of the saved count transformation (labeled **transformation**) to **Export Count Table**.

4. Add the Count Featurizer (deprecated) module to the experiment, and connect it to the two outputs of **Export Count Table**.

5. The Count Featurizer (deprecated) module requires an additional input, for the dataset you want to featurize. Connect the dataset to apply the saved transformation to outputs.

6. Set any necessary parameters for Count Featurizer (deprecated), including the label column, the count columns, the columns to featurize, and the features to output.

    You must select a subset of the columns that were originally selected for the counting transformation. However, the **Export Count Table** module does not provide the list of these columns, so you should review the original experiment and make a note of which columns were used. If you select a column that was not used when creating the transformation, an error is raised.

## Examples

Explore examples of count-based featurization using these sample experiments in the [Azure AI Gallery](https://gallery.azure.ai/):

* [Flight delay prediction](https://gallery.azure.ai/Experiment/Binary-Classification-Flight-delay-prediction-3): Shows how count-based featurization can be useful in a very large dataset.

* [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2): Demonstrates the use of count-based features in a multiclass prediction task.

* [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azure.ai/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2): Uses count-based features in a binary classification task.

> [!NOTE]
> If you open a Gallery experiment created using the deprecated versions of the [Learning with Counts](data-transformation-learning-with-counts.md) modules, the experiment is automatically upgraded to use the newer modules.

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Counting transform|[ITransform interface](itransform-interface.md)|The counting transform.|  

## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dracula count metadata|[Data Table](data-table.md)|The metadata of the counts.|  
|Dracula count table|[Data Table](data-table.md)|The count table.|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0086](errors/error-0086.md)|Exception occurs when a counting transform is invalid.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Learning with Counts](data-transformation-learning-with-counts.md) 
