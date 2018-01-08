---
title: "Select Columns Transform | Microsoft Docs"
ms.custom: ""
ms.date: 10/06/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: aa517da1-4978-43ed-960f-f26cf55bfa95
caps.latest.revision: 6
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Select Columns Transform
*Creates a transformation that selects the same subset of columns as in the given dataset*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
 This article describes how to use the **Select Columns Transform** module in Azure Machine Learning Studio.
 
 The purpose of the **Select Columns Transform** module is to ensure that a predictable, consistent set of columns is always used in downstream machine learning operations. This is particularly important for tasks such as scoring, which require specific columns. Changes in the available columns might break the experiment or change the results.  

You use the **Select Columns Transform** to create and save a set of columns. Then, use the [Apply Transformation](apply-transformation.md) module to apply those selections to new data.


 ## How to Use the Module

This scenario assumes that you intend to use feature selection to generate a dynamic set of columns that will be used for training a model. To ensure that column selections are the same for the scoring process, you use the **Select Columns Transform** module to sapture the column selections and apply them elsewhere in the experiment.
 
1. Add an input dataset, and add an instance of [Filter Based Feature Selection](filter-based-feature-selection.md). 

2. Connect the modules and configure the feature selection module to automatically find some number of best features in a dataset. 

3. Add an instance of [Train Model](train-model.md) and use the output of [Filter Based Feature Selection](filter-based-feature-selection.md) as the input for training.

    > [!IMPORTANT]
    > Because feature importance is decided based on the values in the column, you cannot know in advance which columns might be available for input to [Train Model](train-model.md).  


4. To preserve the columns found by feature selection, attach an instance of the **Select Columns Transform** module. This generates a column selection as a transformation that can be saved or applied to other datasets.  

5. Add the [Score Model](score-model.md) module. Do not connect the input dataset. Instead, add the [Apply Transformation](apply-transformation.md) module, and connect the output of the feature selection transformation. 

   > [!IMPORTANT]
   > You cannot expect to apply [Filter Based Feature Selection](filter-based-feature-selection.md) to the scoring dataset, and get the same results. Since feature selection is based on values, it might choose a different set of columns, which would cause the scoring operation to fail.
    
6. Run the experiment.

This process of saving and then applying a column selection ensures that the same data schema is available for training and scoring.

## Examples

+ For a complete walkthrough that uses this module, see: [Select columns transform](https://gallery.cortanaintelligence.com/Experiment/Select-columns-transform-1)

+ To get a copy of the experiment in your workspace, see [Filter Features And Remove Them From Scoring Inputs](https://gallery.cortanaintelligence.com/Experiment/Filter-Features-And-Remove-Them-From-Scoring-Inputs-1)
   
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset with desired columns|[Data Table](data-table.md)|Dataset containing desired set of columns|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Columns selection transformation|[ITransform interface](itransform-interface.md)|Transformation that selects the same subset of columns as in the given dataset.|  
  
##  <a name="exceptions"></a> Exceptions  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  
  
## See Also  
 [Manipulation](data-transformation-manipulation.md)   
 [Select Columns in Dataset](select-columns-in-dataset.md)   
 [A-Z Module List](a-z-module-list.md)