---
title: "ML Studio (classic): Apply Filter - Azure"
description: Learn how to use the Apply Filter module to transform a column of values by applying a previously defined filter.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"
author: xiaoharper
ms.author: amlstudiodocs 
manager: cgronlun
---
# Apply Filter

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Applies a filter to specified columns of a dataset*  
  
Category: [Data Transformation / Filter](data-transformation-filter.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
##  Module overview  

This article descries how to use the **Apply Filter** module in Machine Learning Studio (classic), to transform a column of values by applying a previously defined filter. Filters are used in digital signal processing to reduce noise or highlight a pattern. Thus, the values that you transform are always numeric, and typically represent some kind of audio or visual signal.  

> [!TIP]
> Are you looking for a different type of filter? Studio (classic) provides these modules for sampling data, getting a subset of data, removing bad values, or creating test and training sets: [Split Data](split-data.md), [Clean Missing Data](clean-missing-data.md), [Partition and Sample](partition-and-sample.md), [Apply SQL Transformation](apply-sql-transformation.md), [Clip Values](clip-values.md).  If you need to filter data as you read it from a source, see [Import Data](import-data.md). The options depend on the source type. 
  
After determining which type of filter is best for your data source, you specify the parameters, and use **Apply Filter** to transform the dataset. Because the design of filters is separate from the process of applying a filter, filters are reusable. For example, if you frequently work with data used for forecasting, you might design several types of moving average filters to train and compare multiple models. You can also save the filter to apply to other experiments or to different datasets.

## How to configure Apply Filter  
  
1.  Add the **Apply Filter** module to your experiment. You can find the IIR filter module under **Data Transformation**, in the **Filters** category.
  
2. To the right-hand input, connect a dataset that contains numeric values to one input.  
  
3. To the left-hand  input, connect an existing filter. You can re-use a saved filter, or you can configure a filter by using one of the following filter modules: [Threshold Filter](threshold-filter.md), [Moving Average Filter](moving-average-filter.md), [Median Filter](median-filter.md), [IIR Filter](iir-filter.md), [FIR Filter](fir-filter.md), [User-Defined Filter](user-defined-filter.md).  
  
3.  In the **Properties** pane of **Apply Filter**, click **Launch column selector** and choose the columns to which the filter should be applied.  
  
4.  Run the experiment, or right-click **Apply Filter** and click **Run selected**.

### Results

The output contains only the data in the selected columns, transformed by applying the specified predefined mathematical transformation.  
  
If you want see other columns in the dataset, you can use the [Add Columns](add-columns.md) module to merge the original and filtered datasets.  
  
> [!NOTE]
>  The values in the original column have not been deleted or overwritten, and are still available in the experiment for reference. However, the output of the filter usually more useful for modeling.

## Examples  

For examples of how filters are used in machine learning, see the [Azure AI Gallery](https://gallery.azure.ai/):  
  
- [Filters](https://go.microsoft.com/fwlink/?LinkId=525732): Demonstrates all filter types, using an engineered waveform dataset.

##  Technical notes  

This section contains implementation details, tips, and answers to frequently asked questions.

-   The **Apply Filter** module binds the specified type of filter to the selected columns. If you need to apply different types of filters to different columns, you should use [Select Columns in Dataset](select-columns-in-dataset.md) to isolate the columns and apply different filter types in separate workflows. For more information, see [Select Columns in Dataset](select-columns-in-dataset.md).  
  
-   The filters do not pass through data columns that are not affected by the filter. That is, the output of **Apply Filter** contains only the transformed numeric values. However, you can use the [Add Columns](add-columns.md) module to join transformed values with the source dataset.  
  
###  Filter periods  

The filter period is determined in part by the filter type, as follows:  
  
-   For finite impulse response (FIR), simple moving average, and triangular moving average filters, the filter period is **finite**.  
  
-   For infinite impulse response (IIR), exponential moving average, and cumulative moving average filters, the filter period is **infinite**.  
  
-   For threshold filters, the filter period is always **1**.  
  
-   For median filters, regardless of the filter period, NaNs and missing values in the input signal do not produce new NaNs in output.  
  
###  Missing values  

This section describes the behavior when missing values are encountered, by filter type. In general, when a filter encounters a NaN or a missing value in the input dataset, the output dataset becomes spoiled with NaNs for some next number of samples, depending on the filter period. This has the following consequences:  
  
-   FIR, simple moving average, or triangular moving average filters have a finite period. As a result, any missing value will be followed by a number of NaNs equal to the filter order minus one.
  
-   IIR, exponential moving average, or cumulative moving average filters have an infinite period. As a result, after the first missing value is encountered, NaNs will continue to propagate indefinitely.  
  
-   In a threshold filter, the period of a threshold filter is 1. As a result, missing values and NaNs do not propagate.
  
-   For median filters, NaNs and missing values encountered in the input dataset do not produce new NaNs in output, regardless of the filter period.  

## Expected inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
|Dataset|[Data Table](data-table.md)|Input dataset|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes). 

## Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Column set|Any|ColumnSelection|NumericAll|Select the columns to filter|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Output dataset|  
  
## See also

 [Filter](data-transformation-filter.md)   
 [A-Z Module List](a-z-module-list.md)
