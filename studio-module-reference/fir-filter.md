---
title: "ML Studio (classic): FIR Filter - Azure"
description: Learn how to use the FIR Filter module to define a kind of filter called a *finite impulse response* (FIR) filter.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# FIR Filter

[!INCLUDE [ML Studio (classic) retirement](../includes/machine-learning-studio-classic-deprecation.md)]

*Creates a finite impulse response filter for signal processing*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview  

This article describes how to use the **FIR Filter** module in Machine Learning Studio (classic), to define a kind of filter called a *finite impulse response* (FIR) filter. FIR filters have many applications in signal processing, and are most commonly used in applications that require a linear-phase response. For example, a filter might be applied to  images used in healthcare to sharpen the overall image, eliminate noise, or focus on an imaged object.

> [!NOTE]
>  A filter is a transfer function that takes an input signal and creates an output signal based on the filter characteristics. For more general information about the user of filters in digital signal processing, see [Filter](data-transformation-filter.md).  

After you have defined a digital signal processing filter, you can apply the filter to data by connecting a dataset and the filter to the [Apply Filter](apply-filter.md) module. You can also save the filter for re-use with similar datasets.

> [!TIP]
> Need to filter data from a dataset or remove missing values? Use these modules instead:  
> 
> - [Clean Missing Data](clean-missing-data.md): Use this module to remove missing values or replace missing values with placeholders.  
> - [Partition and Sample](partition-and-sample.md): Use this module to divide or filter your dataset by criteria such as a range of dates, a specific value, or regular expressions.  
> - [Clip Values](clip-values.md): Use this module to set a range and keep only the values within that range.

## How to configure FIR Filter

1.  Add the **FIR Filter** module to your experiment.  You can find this module under **Data Transformation**, in the **Filter** category.
  
2.  For **Order**, type an integer value that defines the number of active elements used to affect the filter's response. The *order* of the filter represents the length of the filter window.  
  
     For a FIR filter, the minimum order is 4.  
  
3.  For **Window**, select the shape of the data to which the filter will be applied. Machine Learning supports the following types of windowing functions for use in finite impulse response filters:  
  
     **Hamming**: The *generalized Hamming window* provides a type of weighted averaging, which is commonly used in image processing and computer vision.  
  
     **Blackman**: A *Blackman window* applies a smoothly tapered curve function to the signal. The Blackman window has better stopband attenuation than other window types.  
  
     **Rectangular**: A *rectangular window* applies a consistent value inside the specified interval and applies no value elsewhere. The simplest rectangular window might replace *n* values in a data sequence with zeros, which makes it appear as though the signal suddenly turns on and off.  
  
     A rectangular window is also known as a *boxcar* or *Dirichlet window*.  
  
     **Triangular**: A triangular window applies filter coefficients in a step-wise fashion. The current value appears at the peak of the triangle, and then it declines with preceding or following values.  
  
     **None**:  In some applications it is preferable not to use any windowing functions. For example, if the signal you are analyzing already represents a window or burst, applying a window function could deteriorate the signal-to-noise ratio.  
  
4.  For **Filter type**, select an option that defines how the filter is applied. You can specify that the filter exclude the target values, alter the values, reject the values, or pass them through.
  
     **Lowpass**: "Low pass" means that the filter passes through lower values, and removes the higher values. For example, you might use this to remove high-frequency noise and data peaks from a signal. 
     
     This filter type has a smoothing effect on the data.  
  
     **Highpass**: "High pass" means that the filter passes through higher values, and removes lower values. You might use this to remove low frequency data, such as a bias or offset, from a signal. 
     
     This filter type preserves sudden changes and peaks in a signal.
  
     **Bandpass**: "Band pass" means that it passes thorugh the specified band of values, and remove others. You might use this filter to preserve the data from a signal with frequency characteristics at the intersection between the highpass and lowpass filters. 
     
     Bandpass filters are created by combining a highpass and a lowpass filter. The highpass filter cutoff frequency represents the lower cutoff, and the lowpass filter frequency represents the higher cutoff.  
  
    This filter type is good at removing a bias and smoothing a signal.  

     **Bandstop**: "Band stop" means that it blocks specified sigals. In other words, it removes data from a signal with frequency characteristics that are rejected by the low pass and the highpass filters. 
     
     This filter type is good at preserving the signal bias and sudden changes.  
  
5.  Depending on the type of filter you chose, you must set one or more cutoff values.  
  
     Use the **High cutoff**  and **Low cutoff**  options to define an upper and/or a lower threshold for values. One or both of these options are required to specify which values are rejected or passed through. A **bandstop** or **bandpass** filter requires that you set both high and low cutoff values. Other filter types, such as the **lowpass** filter, require that you set only the low cutoff value.
  
6.  Select the **Scale** option if scaling should be applied to coefficients; otherwise leave blank.
  
7.  Connect the filter to [Apply Filter](apply-filter.md), and connect a dataset.  
  
     Use the column selector to specify which columns the filter should be applied to. By default, the [Apply Filter](apply-filter.md) module will use the filter for all selected numeric columns.  
  
8.  Run the experiment.

    No computations are performed until you connect a dataset to the [Apply Filter](apply-filter.md) module and run the experiment. At that point, the specified transformation is applied to the selected numeric columns.
  
> [!NOTE]
> The **FIR Filter** module does not provide the option to create an indicator column. Column values are always transformed in place.

## Examples

For examples of how filters are used in machine learning, see this experiment in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
-  [Filters](https://go.microsoft.com/fwlink/?LinkId=525732): This experiment demonstrates all filter types, using an engineered waveform dataset.

## Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

FIR filters have these characteristics:  
  
+ FIR filters do not have feedback; that is, they use the previous filter outputs.  
+ FIR filters are more stable, because the impulse response will always return to 0.  
+ FIR filters require a higher order to achieve the same selectivity as infinite impulse response (IIR) filters.  
+ Like other filters, the FIR filter can be designed with a specific cutoff frequency that preserves or rejects frequencies that compose the signal.  

### Calculating coefficients over the filter window

The window type determines the trade-off between selectivity (width of the transition band in which frequencies are neither fully accepted nor rejected) and suppression (the total attenuation of frequencies to be rejected). 
The windowing function is applied to the ideal filter response to force the frequency response to zero outside of the window. Coefficients are selected by sampling the frequency response within the window.  

The number of coefficients returned by the **FIR Filter** module is equal to the filter order plus one. The coefficient values are determined by filter parameters and by the windowing method, and are symmetric to guarantee a linear phase response    

###  Scaling of coefficients  

The **FIR Filter** module returns filter coefficients, or tap weights, for the created filter.  
  
The coefficients are determined by the filter, based on the parameters you enter (such as the order). If you want to specify custom coefficients, use the [User-Defined Filter](user-defined-filter.md) module.  
  
When **Scale** is set to **True**, filter coefficients will be normalized, such that the magnitude response of the filter at the center frequency of the passband is 0. The implementation of normalization in Machine Learning Studio (classic) is the same as in the **fir1** function in MATLAB.  

Typically, in the window design method, you design an ideal infinite impulse response (IIR) filter. The window function is applied to the waveform in the time domain, and multiplies the infinite impulse response by the window function. This results in the frequency response of the IIR filter being convolved with the frequency response of the window function. However, in the case of FIR filters, the input and filter coefficients (or tap weights) are convolved when applying the filter.

### Selectivity and stop band attenuation  

The following table compares selectivity with stop band attenuation for a FIR filter with length *n* by using different windowing methods:  

|Window Type|Transition Region|Minimum Stopband Attenuation|  
|-----------------|-----------------------|----------------------------------|  
|Rectangular|0.041n|21 dB|  
|Triangle|0.11n|26 dB|  
|Hann|0.12n|44 dB|  
|Hamming|0.23n|53 dB|  
|Blackman|0.2n|75 dB|  

##  Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Order|>=4|Integer|5|Specify the filter order|  
|Window|Any|WindowType||Specify the type of window to apply|  
|Filter type|Any|FilterType|LowPass|Select the type of filter to create|  
|Low cutoff|[double.Epsilon;.9999999]|Float|0.3|Set the low cutoff frequency|  
|High cutoff|[double.Epsilon;.9999999]|Float|0.7|Set the high cutoff frequency|  
|Scale|Any|Boolean|True|If true, filter coefficients will be normalized|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
  
##  Exceptions
  
|Exception|Description|  
|---------------|-----------------|  
|NotInRangeValue|Exception occurs if parameter is not in range.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).    

## See also  
 [Filter](data-transformation-filter.md)   
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)
