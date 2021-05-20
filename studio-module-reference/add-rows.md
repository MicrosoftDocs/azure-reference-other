---
title: "ML Studio (classic): Add Rows - Azure"
description: Learn how to use the Add Rows module to concatenate two datasets. The rows of the second dataset are added to the end of the first dataset.  
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs 

---
# Add Rows

*Appends a set of rows from an input dataset to the end of another dataset*  

Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview  

This article describes how to use the **Add Rows** module in Azure Machine Learning to concatenate two datasets. In concatenation, the rows of the second dataset are added to the end of the first dataset.  
  
Concatenation of rows is useful in scenarios such as these:  
  
+ You have generated a series of evaluation statistics, and you want to combine them into one table for easier reporting.  
  
+ You have been working with different datasets, and you want to combine the datasets to create a final dataset.  

## How to use Add Rows  

To concatenate rows from two datasets, the rows must have exactly  the same schema. This means, the same number of columns, and the same type of data in the columns.

1.  Drag the **Add Rows** module into your experiment, You can find it under **Data Transformation**,  in the **Manipulate** category.

2. Connect the datasets to the two input ports. The dataset that you want to append should be connected to the second (right) port. 
  
3.  Run the experiment. The number of rows in the output dataset should equal the sum of the rows of both input datasets.

    If you add the same dataset to both inputs of the **Add Rows** module, the dataset is duplicated. 

## Technical notes

This section describes implementation details and common questions.
  
+ You cannot filter the source dataset when adding rows. All the rows from both datasets provided as inputs are concatenated when you use **Add Rows**.  
  
+ If you want to add only a few rows, use [Partition and Sample](partition-and-sample.md) to define a condition by which to filter the rows and generate a dataset with only the rows you want.  

## Examples  

To see examples of how this module is used, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
-  [Demand estimation](https://go.microsoft.com/fwlink/?LinkId=525271): Combines the result of evaluating multiple models into a single dataset and passes it to an Execute R Script for custom processing  
  
- [Breast cancer detection](https://go.microsoft.com/fwlink/?LinkId=525726): Datasets that contain useful features are cleaned and then combined by using **Add Rows**, [Add Columns](add-columns.md), and [Join Data](join-data.md).  
  
- [Prediction of student performance](https://go.microsoft.com/fwlink/?LinkId=525727): Uses **Add Rows** to combine the results of custom metrics that are computed by using [Apply Math Operation](apply-math-operation.md).  
  
- [Time Series Forecasting](https://go.microsoft.com/fwlink/?LinkId=525273): Uses R scripts to generate custom metrics and then combines them in a single table by using **Add Rows**.  
  
## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset1|[Data Table](data-table.md)|Dataset rows to be added to the output dataset first|  
|Dataset2|[Data Table](data-table.md)|Dataset rows to be appended to the first dataset|  
  
## Outputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset that contains all rows of input datasets|  
  
## Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more of input datasets is null or empty.|  
|[Error 0010](errors/error-0010.md)|An exception occurs if input datasets have column names that should match but do not.|  
|[Error 0016](errors/error-0016.md)|An exception occurs if input datasets passed to the module should have compatible column types but do not.|  
|[Error 0008](errors/error-0008.md)|An exception occurs if the parameter is not in range.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).   
## See also
  
 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)
