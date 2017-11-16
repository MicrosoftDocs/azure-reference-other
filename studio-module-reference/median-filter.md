---
title: "Median Filter | Microsoft Docs"
ms.custom: ""
ms.date: 06/21/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a7974d98-616d-4a78-8966-cad384b41886
caps.latest.revision: 19
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Median Filter
*Creates a median filter used to smooth data for trend analysis*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **Median Filter** module to define a *median filter* for applying to a series of values that represent a digital input signal or image.  
  
 In digital signal processing, the use of filters can improve the results of image or voice recognition. Median filters are widely used in image recognition to reduce noise so that features can more easily be detected.  
  
 After you have defined a filter that meets your needs by using the **Median Filter** module, you can apply the filter to data by connecting a dataset and the filter to the [Apply Filter](apply-filter.md) module.  
  
## How to Configure a Median Filter  
  
1.  Add the **Median Filter** to your experiment.  
  
2.  For **Length**, type an integer value that defines the total size of the window across which the filter is applied. This is also called the filter *mask*.  
  
     The value must be an odd, positive-valued integer. If you specify an even number, the mask size is reduced by one.  
  
     By default the mask begins at the current value and extends **forward** for the specified number of units. In other words, it creates a *one-sided average*.  
  
     For example, if you type 20, the median value is computed across a sliding window consisting of 20 values beginning with the current value.  
  
3.  Connect the filter to [Apply Filter](apply-filter.md), and connect a dataset.  
  
     Use the column selector to specify which columns of the dataset to which the filter should be applied. By default, the [Apply Filter](apply-filter.md) module will use the filter for all selected numeric columns.  
  
4.  Run the experiment.  
  
     At that point, the following operations are applied to the selected columns:  
  
    -   For each set of values included in the window or mask, the filter algorithm computes the median.  
  
    -   The current (or index) value is replaced with the median value.  
  
## Examples  
 For examples of how filters are used in machine learning, see this experiment in the [Cortan Analytics Gallery](http://gallery.cortanaintelligence.com):  
  
-   The [Filters](http://go.microsoft.com/fwlink/?LinkId=525732) sample demonstrates all filter types, using an engineered waveform dataset for illustration.  
  
## Technical Notes  
 Each entry in the output signal is equal to the median of the entries in a subset (mask) of the input signal, and centered at the corresponding index. The mask size should be an odd, positive-valued integer.  
  
 If you provide this method with an even-valued mask size, it is reduced by one. For example, given m=2q+1, the filter is defined as:  
  
 yi =median[{xi-q,…, xi+q}]  
  
 Values beyond the borders of the input signal are assumed to equal the value at the border:  
  
 ![values beyond borders of median filter](media/aml-medianfilterborder.png "AML_MedianFilterBorder")  
  
 where n is the length of the input signal.  
  
 For more information about median filters, this Wikipedia article provides a good explanation of the theory and application:  
  
 [Wikipedia: Median Filters](http://en.wikipedia.org/wiki/Median_filter)  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Length|>=1|Integer|5|Length of the filter window|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
  
## See Also  
 [Filter](data-transformation-filter.md)   
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)