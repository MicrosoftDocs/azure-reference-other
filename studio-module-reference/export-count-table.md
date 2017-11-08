---
title: "Export Count Table | Microsoft Docs"
ms.custom: ""
ms.date: 04/11/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: dfe32418-04e8-407d-88fc-eadbc78e3148
caps.latest.revision: 8
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Export Count Table
*Exports the count table from a saved transformation for use with new data*  
  
 Category: [Learning with Counts](data-transformation-learning-with-counts.md)  
  
## Module Overview  
 The **Export Count Table** module is provided for backward compatibility with experiments that use the [Build Count Table (deprecated)](build-count-table-deprecated.md) and [Count Featurizer (deprecated)](count-featurizer-deprecated.md) modules.  
  
 When you use [Build Counting Transform](build-counting-transform.md) to create count-based features, the module outputs both a featurized dataset and a *transform* that creates features from counts. You can use **Export Count Table** to separate the count-based features into the two inputs used in previous experiments: **count metadata** and a **count table**.  
  
 For general information about count tables and how they are used to create features, see [Learning with Counts](data-transformation-learning-with-counts.md).  
  
## How to Configure Export Count Table  
  
1.  Open the experiment where you want to use the imported count table.  
  
2.  Locate the saved count transformation, and add it to the experiment.  
  
3.  Connect the output of the saved count transformation (labeled **transformation**) to **Export Count Table**.  
  
4.  Add the [Count Featurizer (deprecated)](count-featurizer-deprecated.md) module to the experiment, and connect it to the two outputs of **Export Count Table**.  
  
5.  [Count Featurizer (deprecated)](count-featurizer-deprecated.md) requires an additional input, for the dataset you want to featurize. Connect the dataset to apply the saved transformation to outputs.  
  
6.  Set any necessary parameters for [Count Featurizer (deprecated)](count-featurizer-deprecated.md), including the label column, the count columns, the columns to featurize, and the features to output.  
  
     Note that you must select a subset of the columns that were originally selected for the counting transformation. However, the **Export Count Table** module does not provide the list of these columns, so you should review the original experiment and make a note of which columns were used. If you select a column that was not used when creating the transformation, you will get an error.  
  
## Examples  
 You can see how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Learning with Counts: Binary Classification](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-Classification-2) sample demonstrates how to use the learning with counts modules to generate features from columns of categorical values for a binary classification model.  
  
-   The [Learning with Counts: Multiclass classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Multiclass-classification-with-NYC-taxi-data-2) sample demonstrates how to use the learning with counts modules for performing multiclass classification on the publicly available NYC taxi dataset. The sample uses a Multiclass logistic regression learner to model this problem.  
  
-   The [Learning with Counts: Binary classification with NYC taxi data](https://gallery.azureml.net/Experiment/Learning-with-Counts-Binary-classification-with-NYC-taxi-data-2) sample demonstrates how to use the learning with counts modules for performing binary classification on the publicly available NYC taxi dataset. The sample uses a two-class logistic regression learner to model this problem.  
  
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