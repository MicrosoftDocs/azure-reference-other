---
title: "ML Studio (classic): Apply Transformation - Azure"
description: Learn how to use the Apply Transformation module to modify an input dataset based on a previously computed transformation. 
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs 
manager: cgronlun
---
# Apply Transformation

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Applies a well-specified data transformation to a dataset*  

Category: [Machine Learning / Score](machine-learning-score.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview  

This article describes how to use the [Apply Transformation](apply-transformation.md) module in Machine Learning Studio (classic), to modify an input dataset based on a previously computed transformation.  
  
For example, if you used z-scores to normalize your training data by using the [Normalize Data](normalize-data.md) module, you would want to use the z-score value that was computed for training during the scoring phase as well. In Machine Learning Studio (classic), you can do this easily by saving the normalization method as a transform, and then using [Apply Transformation](apply-transformation.md) to apply the z-score to the input data before scoring.
  
Machine Learning Studio (classic) provides support for creating and then applying many different kinds of custom transformations. For example, you might want to save and then re-use transformations that do the following:  
  
- Remove or replace missing values, using [Clean Missing Data](clean-missing-data.md)  
  
- Bin, scale, and normalize data, using [Normalize Data](normalize-data.md) or [Group Data into Bins](group-data-into-bins.md)  
  
- Create a set of compact features by calculating joint probability distribution for a dataset, using the [Learning with Counts](data-transformation-learning-with-counts.md) modules.  

## How to use Apply Transformation  
  
1. Add the [Apply Transformation](apply-transformation.md) module to your experiment. You can find thi module under **Machine Learning**, in the **Score** category. 
  
2. Locate an existing transformation to use as an input.  
  
     If the transformation was created earlier in the experiment (for example, as part of a cleaning or data scaling operation) typically the [ITransform interface](itransform-interface.md) object is available on the module's right-hand output. Connect that output to the left-hand input of [Apply Transformation](apply-transformation.md).  
  
     Previously saved transformations can be found in the **Transforms** group in the left navigation pane.  
  
    > [!TIP]
    > If you design a transformation for an experiment but do not explicitly save it, the transformation is available in the workspace as long as your session is open. If you close the session but do not save the transformation, you can re-run the experiment to generate the [ITransform interface](itransform-interface.md) object.  
  
3. Connect the dataset that you want to transform. The dataset should have exactly the same schema (number of columns, column names, data types) as the dataset for which the transformation was first designed.  
  
4. No other parameters need to be set; all customization is done when defining the transformation.  
  
5. To apply a transformation to the new dataset, run the experiment.  
  
## Examples  

To see how this module is used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Online Fraud Detection](https://gallery.azure.ai/Experiment/8e9fe4e03b8b4c65b9ca947c72b8e463): This sample demonstrates how to use **Apply Transformation** with [Clean Missing Data](clean-missing-data.md), to ensure that missing values are handled the same in all datasets.  

- [Predictive Maintenance](https://gallery.azure.ai/Experiment/df7c518dcba7407fb855377339d6589f): Demonstrates how to use **Apply Transformation** with [Normalize Data](normalize-data.md).  
  
- [Learning with Counts](https://gallery.azure.ai/Experiment/47deb75fc7bb428194e9d0d5713350c8): Uses **Apply Transformation** to reuse a count table.  

##  Technical notes  

The **Apply Transformation** module can take as input the output of any module that creates an [ITransform interface](itransform-interface.md). These modules include:  
  
- [Clean Missing Data](clean-missing-data.md)  
  
- [Normalize Data](normalize-data.md)  
  
- [Group Data into Bins](group-data-into-bins.md)  
  
- [Learning with Counts](data-transformation-learning-with-counts.md)  

> [!TIP]
> You can also save and re-use filters designed for digital signal processing. However, filters use the [IFilter interface](ifilter-interface.md) interface, rather than [ITransform interface](itransform-interface.md).  
  
## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Transformation|[ITransform interface](itransform-interface.md)|A unary data transformation|  
|Dataset|[Data Table](data-table.md)|Dataset to be transformed|  
  
## Outputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Transformed dataset|[Data Table](data-table.md)|Transformed dataset|  
  
## Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0003](errors/error-0003.md)|Exception occurs if one or more of inputs are null or empty.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also
  
 [Filter](data-transformation-filter.md)   
 [Apply SQL Transformation](apply-sql-transformation.md)   
 [Clean Missing Data](clean-missing-data.md)   
 [Normalize Data](normalize-data.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Group Data into Bins](group-data-into-bins.md)
