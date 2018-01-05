---
title: "Export Count Table | Microsoft Docs"
ms.custom: ""
ms.date: 12/18/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: dfe32418-04e8-407d-88fc-eadbc78e3148
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Export Count Table
*Exports the count table from a saved transformation for use with new data*  
  
 Category: [Learning with Counts](data-transformation-learning-with-counts.md)  
  
## Module Overview

This article describes how to use the **Export Count Table** module in Azure Machine Learning Studio. The **Export Count Table** module is provided for backward compatibility with experiments that use the [Build Count Table (deprecated)](build-count-table-deprecated.md) and [Count Featurizer (deprecated)](count-featurizer-deprecated.md) modules.
  
When you use the new [Build Counting Transform](build-counting-transform.md) module to create count-based features, the module outputs both a featurized dataset and a *transform* that creates features from counts. By using the **Export Count Table** module, you can separate the count-based features output by this newer module into **count metadata** and a **count table**. These output formats were used by earlier, now deprecated modules:
  
For general information about count tables and how they are used to create features, see [Learning with Counts](data-transformation-learning-with-counts.md).  

 >  For all new experiments, we recommend that you use the following modules:  
>   
>  -   [Build Counting Transform](build-counting-transform.md)  
> -   [Modify Count Table Parameters](modify-count-table-parameters.md)  
> -   [Merge Count Transform](merge-count-transform.md)  

## How to Configure Export Count Table  
  
1.  In Azure Machine Learning Studio, open the experiment where you want to use the imported count table.  
  
2.  Locate the saved count transformation, and add it to the experiment.  
  
3.  Connect the output of the saved count transformation (labeled **transformation**) to **Export Count Table**.  
  
4.  Add the [Count Featurizer (deprecated)](count-featurizer-deprecated.md) module to the experiment, and connect it to the two outputs of **Export Count Table**.  
  
5.  [Count Featurizer (deprecated)](count-featurizer-deprecated.md) requires an additional input, for the dataset you want to featurize. Connect the dataset to apply the saved transformation to outputs.  
  
6.  Set any necessary parameters for [Count Featurizer (deprecated)](count-featurizer-deprecated.md), including the label column, the count columns, the columns to featurize, and the features to output.  
  
     Note that you must select a subset of the columns that were originally selected for the counting transformation. However, the **Export Count Table** module does not provide the list of these columns, so you should review the original experiment and make a note of which columns were used. If you select a column that was not used when creating the transformation, you will get an error.  
  
## Examples

Explore examples of count-based featurization using these sample experiments in the [Cortana Intelligence Gallery](https://gallery.cortanaintelligence.com/):
  
-   The [flight delay prediction](http://go.microsoft.com/fwlink/?LinkId=525277) sample shows how count-based featurization can be useful in a very large dataset.
- [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.cortanaintelligence.com/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2) demonstrates the use of count-based features in a multiclass prediction task.
- The [Learning with Counts: Binary classification with NYC taxi data](https://gallery.cortanaintelligence.com/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2) sample uses count-based features in a binary classification task.

> [!NOTE]
> 
> If you open a Gallery experiment created using the deprecated versions of the [Learning with Counts](data-transformation-learning-with-counts.md) modules, the experiment is automatically upgraded to use the newer modules.
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Counting transform|[ITransform interface](itransform-interface.md)|The counting transform.|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dracula count metadata|[Data Table](data-table.md)|The metadata of the counts.|  
|Dracula count table|[Data Table](data-table.md)|The count table.|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
|[Error 0086](errors/error-0086.md)|Exception occurs when a counting transform is invalid.|  
  
## See Also  
 [Learning with Counts](data-transformation-learning-with-counts.md)   
 [Count Featurizer (deprecated)](count-featurizer-deprecated.md)