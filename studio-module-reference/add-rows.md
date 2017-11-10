---
title: "Add Rows | Microsoft Docs"
ms.custom: ""
ms.date: 09/21/2017
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: b2ebdabd-217d-4915-86cc-5b05972f7270
caps.latest.revision: 15
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Add Rows
*Appends a set of rows from an input dataset to the end of another dataset*  
  
 Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  
  
##  <a name="Remarks"></a> Module Overview  

This article describes how to use the **Add Rows** module in Azure Machine Learning to concatenate two datasets. In concatenation, the rows of the second dataset are added to the end of the first dataset.  
  
 Concatenation of rows is useful in scenarios such as these:  
  
-   You have generated a series of evaluation statistics, and you want to combine them into one table for easier reporting.  
  
-   You have been working with different datasets, and you want to combine the datasets to create a final dataset.  
  

## How to Use Add Rows  
  
1.  Drag the Add Rows module into your experiment, You can find it under **Data Transformation**, **Manipulate**.

2. Connect the datasets to the two input ports. The dataset that you want to append should be connected to the second (right) port.  

    When adding two datasets together, these rules apply:  
  
    -   To concatenate rows together, the rows must have the same schema. This means, the same number of columns, and the same type of data in the columns.  
  
    -   If you add the same dataset to both inputs of the **Add Rows** module, the dataset will be duplicated.  
  
3.  Run the experiment.  

    The number of rows in the output dataset should equal the sum of the rows of both input datasets.  
  

## Technical Notes

This section describes implementation details and common questions.
  
-   You cannot filter the source dataset when adding rows. All the rows from both datasets provided as inputs are concatenated when you use **Add Rows**.  
  
     If you want to add only a few rows, use [Partition and Sample](partition-and-sample.md) to define a condition by which to filter the rows and generate a dataset with only the rows you want.  
  
## Examples  
 You can see examples of how this module is used by exploring these sample experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Demand estimation](http://go.microsoft.com/fwlink/?LinkId=525271) sample combines the result of evaluating multiple models into a single dataset and passes it to an Execute R Script for custom processing  
  
-   In the [Breast cancer detection](http://go.microsoft.com/fwlink/?LinkId=525726) sample, datasets that contain useful features are cleaned and then combined by using **Add Rows**, [Add Columns](add-columns.md), and [Join Data](join-data.md).  
  
-   The [Prediction of student performance](http://go.microsoft.com/fwlink/?LinkId=525727) sample uses **Add Rows** to combine the results of custom metrics that are computed by using [Apply Math Operation](apply-math-operation.md).  
  
-   The [Time Series Forecasting](http://go.microsoft.com/fwlink/?LinkId=525273) sample uses R scripts to generate custom metrics and then combines them in a single table by using **Add Rows**.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset1|[Data Table](data-table.md)|Dataset rows to be added to the output dataset first|  
|Dataset2|[Data Table](data-table.md)|Dataset rows to be appended to the first dataset|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset that contains all rows of input datasets|  
  
##  <a name="exceptions"></a> Exceptions  
 For a list of all exceptions, see [Module Error Codes](machine-learning-module-error-codes.md).  
  
|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of input datasets is null or empty.|  
|[Error 0010](errors/error-0010.md)|An exception occurs if input datasets have column names that should match but do not.|  
|[Error 0016](errors/error-0016.md)|An exception occurs if input datasets passed to the module should have compatible column types but do not.|  
|[Error 0008](errors/error-0008.md)|An exception occurs if the parameter is not in range.|  
  
## See Also  
 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)