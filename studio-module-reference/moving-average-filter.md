---
title: "ML Studio (classic): Moving Average Filter - Azure"
description: Learn how to use the Moving Average Filter module to calculate a series of one-sided or two-sided averages over a dataset, using a window length that you specify.  
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Moving Average Filter
*Creates a moving average filter used to smooth data for trend analysis*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview

This article describes how to use the **Moving Average Filter** module in Machine Learning Studio (classic), to calculate a series of one-sided or two-sided averages over a dataset, using a window length that you specify.  
  
After you have defined a filter that meets your needs, you can apply it to selected columns in a dataset by connecting it to the [Apply Filter](apply-filter.md) module. The module does all the calculations and replaces values within numerical columns with corresponding moving averages.  
  
You can use the resulting moving average for plotting and visualization, as a new smooth baseline for modeling, for calculating variances against calculations for similar periods, and so on.  

> [!TIP]
> Need to filter data from a dataset or remove missing values? Use these modules instead:  
> 
> - [Clean Missing Data](clean-missing-data.md): Use this module to remove missing values or replace missing values with placeholders.  
> - [Partition and Sample](partition-and-sample.md): Use this module to divide or filter your dataset by criteria such as a range of dates, a specific value, or regular expressions.  
> - [Clip Values](clip-values.md): Use this module to set a range and keep only the values within that range.

## Understanding and using moving averages

This type of average helps you reveal and forecast useful temporal patterns in retrospective and real-time data. The simplest type of moving average starts at some sample of the series, and uses the average of that position plus the previous n positions instead of the actual value. (You can define n as you like.) The longer the period n across which the average is computed, the less variance you will have among values. Also, as you increase the number of values used, the less effect any single value has on the resulting average.  

A moving average can be *one-sided* or *two-sided*. In a one-sided average, only values preceding the index value are used. In a two-sided average, past and future values are used.  

For scenarios in which you are reading streaming data, cumulative and weighted moving averages are particularly useful. A *cumulative moving average* takes into account the points preceding the current period.  

You can weight all data points equally when computing the average, or you can ensure that values nearer the current data point are weighted more strongly. In a *weighted moving average*, all weights must sum to 1.  

In an *exponential moving average*, the averages consist of a *head* and a *tail*, which can be weighted. A lightly weighted tail means that the tail follows the head quite closely, so the average behaves like a moving average on a short weighting period. When tail weights are heavier, the average behaves more like a longer simple moving average.  

## How to configure Moving Average Filter  

1.  Add the **Moving Average Filter** module to your experiment.  You can find this module under **Data Transformation**, in the **Filter** category.
  
2.  For **Length**, type a positive whole number value that defines the total size of the window across which the filter is applied. This is also called the filter *mask*. For a moving average, the length of the filter determines how many values are averaged in the sliding window.
  
     Longer filters are also called *higher order* filters, and provide a larger window of calculation and a closer approximation of the trend line.  
  
     Shorter or *lower order* filters use a smaller window of calculation and more closely resemble the original data.  
  
3.  For **Type**, choose the type of moving average to apply.  
  
    Machine Learning Studio (classic) supports the following types of moving average calculations:  
  
     **Simple**: A simple moving average (SMA) is calculated as an unweighted rolling mean.  
  
     **Triangular**: Triangular moving averages (TMA) are averaged twice for a smoother trend line.  The word triangular is derived from the shape of the weights that are applied to the data, which emphasizes central values.  
  
     **Exponential Simple**: An exponential moving average (EMA) gives more weight to the most recent data. The weighting drops off exponentially.  
  
     **Exponential**: A modified exponential moving average calculates a running moving average, where calculating the moving average at any one point considers the previously computed moving average at all preceding points. This method yields a smoother trend line.  
  
     **Cumulative**:  Given a single point and a current moving average, the cumulative moving average (CMA) calculates the moving average at the current point.  
  
4.  Add the dataset that has the values you want to compute a moving average for, and add the [Apply Filter](apply-filter.md) module.  
  
     Connect the **Moving Average Filter** to the left-hand input of [Apply Filter](apply-filter.md), and connect the dataset to the right-hand input.  
  
5.  In the [Apply Filter](apply-filter.md) module, use the column selector to specify which columns the filter should be applied to. By default, the filter transformation is applied to all numeric columns, so be sure to exclude any columns that don’t have appropriate data.  
  
6.  Run the experiment.
  
     For each set of values defined by the filter length parameter, the current (or index) value is replaced with the moving average value.  
  
## Examples

For examples of how filters are used in machine learning, see this experiment in the [Azure AI Gallery](https://gallery.azure.ai/):
  
-  [Filters](https://go.microsoft.com/fwlink/?LinkId=525732): This experiment demonstrates all filter types, using an engineered waveform dataset.

##  Module parameters
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Length|>=1|Integer|5|Set the length of the moving average window|  
|Type|Any|MovingAverageType||Specify the type of moving average to create|  
  
##  Outputs  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
  
## See also  
 [Filter](data-transformation-filter.md)   
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)   
 [Additional filter samples](https://gallery.azureml.net/browse?s=moving%20average%20filter)
