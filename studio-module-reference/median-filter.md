---
title: "Median Filter | Microsoft Azure Docs"
ms.custom: ""
ms.date: 01/11/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a7974d98-616d-4a78-8966-cad384b41886
caps.latest.revision: 19
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Median Filter
*Creates a median filter used to smooth data for trend analysis*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  
  
## Module overview  

This article describes how to use the **Median Filter** module in Azure Machine Learning Studio, to define a *median filter*. This type of filter is used in digital signal processing, to modify a series of values that represent a digital input signal or image.
  
Filters are an important tool in digital signal processing, and are used to improve the results of image or voice recognition. Median filters can be applied in image recognition, to reduce noise across pixels so that features can more easily be detected.

## How to use Median Filter  

First, you define a filter specification that meets your needs by using the **Median Filter** module. Then, you apply the filter to data by connecting a dataset and the filter to the [Apply Filter](apply-filter.md) module.

1.  Add the **Median Filter** to your experiment in Azure Machine Learning Studio. You can find this module under **Data Transformation**, **Filter**. 
  
2.  For **Length**, type an integer value that defines the total size of the window across which the filter is applied. This is also called the filter *mask*.  
  
     The value should be an odd, positive-valued integer. If you specify an even number, the mask size is reduced by one.  Any number of 3 or less results in no change to the values.
  
     By default the mask begins at the current value and creates a window centered on the current value.  
  
     For example, if you type 5 as the **Length** or window size, the median value is computed across a sliding window consisting of 5 values centered on the current value. If you type 4, the mask is reduced to 3 values, centered on the index value.

3.  Connect the filter to [Apply Filter](apply-filter.md), and connect a dataset.  
  
     Use the column selector to specify which columns of the dataset to which the filter should be applied. By default, the [Apply Filter](apply-filter.md) module will use the filter for all selected numeric columns.  
  
4.  Run the experiment, or click just the **Median Filter** module and select **Run Selected**.  

### Results

When the filter is applied,the following operations are applied to the selected columns:  
  
+ For each set of values included in the window or mask, the filter algorithm computes the median.

+ The current (or index) value is replaced with the median value.  

The actual values in the source dataset are unchanged. The **Median Filter** module creates new values that you can use in subsequent machine learning tasks. Depending on how you configure the [Apply Filter](apply-filter.md) module, you can either append the filter results to the dataset in a new column, or output just the changed values.

For example, the following table shows the results of a filter applied to a series of numbers. Two different mask lengths (3 and 5) were used. The outputs were combined with the source values by using the [Add Columns](add-columns.md) module. 

|index|	Source value|	Mask = 3|	Mask = 5|
|----|----|----|----|
|1	|37.4|	37.4|	37.4|
|2	|28.8|	28.8|	28.8|
|3|	26.2|	28.6|	28.6|
|4|	28.6|	26.4|	27.4|
|5|	26.4|	27.4|	27.4|
|6|	27.4	|27.4|	28.6|
|7|	29.4|	29.4|	29.4|
|8|	40.4|	38	|36.4|
|9|	38	|38|	38|
|10|	36.4|	38|	40.4|
|11|	48	|41.4|	38|


## Examples  

For examples of how filters are used in machine learning, see the [Azure AI Gallery](http://gallery.cortanaintelligence.com):  
  
- [Filters](http://go.microsoft.com/fwlink/?LinkId=525732): Demonstrates all filter types, using an engineered waveform dataset for illustration.

## Technical notes
 
Each entry in the output signal is equal to the median of the entries in a subset (mask) of the input signal, and **centered** at the corresponding index. The mask size should be an odd, positive-valued integer.
  
If you provide this method with an even-valued mask size, it is reduced by one. For example, given `m=2q+1`, the filter is defined as:  `yi =median[{xi-q,…, xi+q}]`
  
Values beyond the borders of the input signal are assumed to equal the value at the border. That is, if _n_ is the length of the input signal: 

 ![values beyond borders of median filter](media/aml-medianfilterborder.png "AML_MedianFilterBorder")  

For more information about median filters, this Wikipedia article provides a good explanation of the theory and application:  
  
 [Wikipedia: Median Filters](http://en.wikipedia.org/wiki/Median_filter)  
  
##  <a name="parameters"></a> Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Length|>=1|Integer|5|Length of the filter window|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
  
## See also  
 [Filter](data-transformation-filter.md)   
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)