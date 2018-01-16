---
title: "Moving Average Filter | Microsoft Docs"
titleSuffix: "Azure Machine Learning Studio"
ms.custom: ""
ms.date: 01/11/2018
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1889e4ca-7bf7-494d-b2cc-da9940468b9e
caps.latest.revision: 21
author: "jeannt"
ms.author: "jeannt"
manager: "cgronlund"
---
# Moving Average Filter
*Creates a moving average filter used to smooth data for trend analysis*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  
  
## Module overview  

This article describes how to use the **Moving Average Filter** module in Azure Machine Learning Studio, to calculate a series of one-sided or two-sided averages over a dataset, using a window length that you specify.  

Filters are an important tool in digital signal processing, and are often used in machine learning to improve the results of image or voice recognition. In general, a filter is a transfer function that takes an input signal and creates an output signal based on the filter characteristics. For more general information about the user of filters in digital signal processing, see [Filter](data-transformation-filter.md).

**Moving average filters** are useful in a wide range of machine learning tasks. For example, you can use the averaged values for plotting and visualization, as a new smooth baseline for modeling, or for calculating variances against calculations for similar periods.

To create a moving avergae, you define a filter usng this module, and connect it to the [Apply Filter](apply-filter.md) module, along with the dataset you want to modify. The [Apply Filter](apply-filter.md) module performs the calculations specified by the **Moving Average Filter** mdoule and replaces values in the specified columns with the moving average values.
  
### More about moving averages  

A moving average helps reveal and forecast useful temporal patterns in retrospective and real-time data.  
  
The simplest type of moving average starts at some sample of the series, and uses the average of that position plus the previous _n_ positions, instead of the actual value. You can define _n_ as any value; the longer the period _n_ that is averaged, the less variance you get among series values. As you increase the number of values used, the less effect any single value has on the resulting average.
  
A moving average can be *one-sided* or *two-sided*. 

+ In a one-sided average, only values preceding the index value are used. 
+ In a two-sided average, past and future values are used.  
  
For scenarios in which you are reading streaming data, cumulative and weighted moving averages are particularly useful. A *cumulative moving average* takes into account the points preceding the current period. 
  
You can weight all data points equally when computing the average, or you can ensure that values nearer the current data point are weighted more strongly. In a *weighted moving average*, all weights must sum to 1.  
  
In an *exponential moving average*, the averages consist of a *head* and a *tail*, which can be weighted. A lightly weighted tail means that the tail follows the head quite closely, so the average behaves like a moving average on a short weighting period. When tail weights are heavier, the average behaves more like a longer simple moving average.  
  
## How to configure Moving Average Filter  
  
1.  Add the **Moving Average Filter** module to your Studio experiment. You can find it under **Data Transformation**, in the **Filters** category. 
  
2.  For **Length**, type a positive whole number value that defines the total size of the window across which the filter is applied. This is also called the filter *mask*.  
  
     For a moving average, the length of the filter determines how many values are averaged in the sliding window.  
  
     Longer filters are also called *higher order* filters, and provide a larger window of calculation and a closer approximation of the trend line.  
  
     Shorter or *lower order* filters use a smaller window of calculation and more closely resemble the original data.  
  
3.  For **Type**, choose the type of moving average to apply.  
  
    Azure Machine Learning Studio supports the following types of moving average calculations:  
  
     + **Simple**: 
     
         A simple moving average (SMA) is calculated as an unweighted rolling mean.  
  
     + **Triangular**  
     
         Triangular moving averages (TMA) are averaged twice for a smoother trend line.  The word triangular is derived from the shape of the weights that are applied to the data, which emphasizes central values.  
  
     + **Exponential Simple**  
     
         An exponential moving average (EMA) gives more weight to the most recent data. The weighting drops off exponentially.  
  
     + **Exponential**  
     
         A modified exponential moving average calculates a running moving average, in which calculating the moving average at any one point considers the previously computed moving average at all preceding points. This method yields a smoother trend line.  
  
     + **Cumulative**  
     
         Given a single point and a current moving average, the cumulative moving average (CMA) calculates the moving average at the current point.  
  
4.  Add the dataset that has the values you want to compute a moving average for, and add the [Apply Filter](apply-filter.md) module.  
  
     Connect the **Moving Average Filter** to the left-hand input of [Apply Filter](apply-filter.md), and connect the dataset to the right-hand input.  
  
5.  In the [Apply Filter](apply-filter.md) module, use the column selector to specify which columns the filter should modify. 

    By default, the filter is applied to all numeric columns. Be sure to exclude any columns that don’t have appropriate data.
  
6.  Run the experiment.  
  
     At that point, for each set of values defined by the filter length parameter, the current (or index) value is replaced with the moving average value.  
  
## Examples  
 
For examples of how filters are used in machine learning, see the [Azure AI Gallery](https://gallery.cortanaintelligence.com/):  
  
-   [Filters](http://go.microsoft.com/fwlink/?LinkId=525732): Demonstrates all filter types, using an engineered waveform dataset.  
  
##  <a name="parameters"></a> Module parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Length|>=1|Integer|5|Set the length of the moving average window|  
|Type|Any|MovingAverageType||Specify the type of moving average to create|  
  
##  <a name="Outputs"></a> Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
  
## See also  
 [Filter](data-transformation-filter.md)   
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Additional filter samples](https://gallery.azureml.net/browse?s=moving%20average%20filter)