---
title: "Apply Filter | Microsoft Docs"
ms.custom: ""
ms.date: 04/12/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 278e11ec-cb16-49d4-a13c-54b2c9f5ce88
caps.latest.revision: 18
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Apply Filter
*Applies a filter to specified columns of a dataset*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Apply Filter** module to transform a column of numbers that typically represents some kind of audio or image signal), by applying a previously defined filter. Filters of this kind are used in digital signal processing to reduce noise or highlight a pattern.  
  
 The **Apply Filter** module returns a dataset that has been transformed by applying the filter. Because the design of filters is separate from the process of applying a filter, filters are reusable. For example, if you frequently work with data used for forecasting, you might design several types of moving average filters to train and compare multiple models. For more information, see [Moving Average Filter](moving-average-filter.md).  
  
 After determining which type of filters work best for your data source, you can save the workflow to apply to other experiments or to different datasets.  
  
> [!TIP]
>  Need to filter data from a dataset or remove missing values? Use these modules instead:  
>   
>  -   [Clean Missing Data](clean-missing-data.md)  
>   
>      Use this module to remove missing values or replace missing values with placeholders.  
> -   [Partition and Sample](partition-and-sample.md)  
>   
>      Use this module to divide or filter your dataset by criteria such as a range of dates, a specific value, or regular expressions.  
> -   [Clip Values](clip-values.md).  
>   
>      Use this module to set a range and keep only the values within that range.  
  
## How to Configure Apply Filter  
  
1.  Add the **Apply Filter** module to your experiment.  
  
     To the right-hand input, connect a dataset that contains numeric values to one input.  
  
     To the left-hand  input, connect an existing filter. You can re-use a saved filter, or you can configure a filter by using one of the following filter modules: [Threshold Filter](threshold-filter.md), [Moving Average Filter](moving-average-filter.md), [Median Filter](median-filter.md), [IIR Filter](iir-filter.md), [FIR Filter](fir-filter.md), [User-Defined Filter](user-defined-filter.md).  
  
2.  For **Column set**, click **Launch column selector** and choose the columns to which the filter will be applied.  
  
3.  Run the experiment.  
  
4.  The module's output contains only the data in the selected columns, transformed by applying the specified predefined mathematical transformation.  
  
     If you want see other columns in the dataset, you can use the [Add Columns](add-columns.md) module to merge the original and filtered datasets.  
  
    > [!NOTE]
    >  The values in the original column have not been deleted or overwritten, and are still available in the experiment for reference. However, the output of the filter usually more useful for modeling.  
  
## Examples  
 For examples of how filters are used in machine learning, see this experiment in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Filters](http://go.microsoft.com/fwlink/?LinkId=525732) sample demonstrates all filter types, using an engineered waveform dataset for illustration.  
  
##  <a name="Notes"></a> Technical Notes  
  
-   The **Apply Filter** module binds the specified type of filter to the selected columns. If you need to apply different types of filters to different columns, you should use [Select Columns in Dataset](select-columns-in-dataset.md) to isolate the columns and apply different filter types in separate workflows. For more information, see [Select Columns in Dataset](select-columns-in-dataset.md).  
  
-   The filters do not pass through data columns that are not affected by the filter. That is, the output of **Apply Filter** contains only the transformed numeric values. However, you can use the [Add Columns](add-columns.md) module to join transformed values with the source dataset.  
  
###  <a name="filterperiod"></a> Filter Periods  
 The filter period is determined in part by the filter type, as follows:  
  
-   For finite impulse response (FIR), simple moving average, and triangular moving average filters, the filter period is **finite**.  
  
-   For infinite impulse response (IIR), exponential moving average, and cumulative moving average filters, the filter period is **infinite**.  
  
-   For threshold filters, the filter period is always **1**.  
  
-   For median filters, regardless of the filter period, NaNs and missing values in the input signal do not produce new NaNs in output.  
  
###  <a name="missingvalues"></a> How Missing Values are Handled  
 If a filter encounters a NaN or a missing value in the input dataset, the output dataset becomes spoiled with NaNs for some next number of samples, depending on the filter period. This has the following consequences:  
  
-   FIR, simple moving average, or triangular moving average filters have a finite period; thus, any missing value will be followed by a number of NaNs equal to the filter order minus one.  
  
-   IIR, exponential moving average, or cumulative moving average filters have an infinite period; thus, after the first missing value is encountered, NaNs will continue to propagate indefinitely.  
  
-   Because the period of a threshold filter equals 1, missing values and NaNs do not propagate.  
  
-   For median filters, NaNs and missing values encountered in the input dataset do not produce new NaNs in output, regardless of the filter period.  
  
##  <a name="ExpectedInputs"></a> Expected Inputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Column set|Any|ColumnSelection|NumericAll|Select the columns to filter|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Output dataset|  
  
## See Also  
 [Filter](data-transformation-filter.md)   
 [A-Z Module List](a-z-module-list.md)