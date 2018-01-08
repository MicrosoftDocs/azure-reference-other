---
title: "FIR Filter | Microsoft Docs"
ms.custom: ""
ms.date: 04/12/2016
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 5bcfd02b-e359-4289-b75c-3aa9f3e4479f
caps.latest.revision: 20
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# FIR Filter
*Creates a finite impulse response filter for signal processing*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **FIR Filter** module to define a kind of filter called a *finite impulse response* (FIR) filter. FIR filters have many applications in signal processing, and are most commonly used in applications that require a linear-phase response. For example, a filter might be applied to  images used in healthcare to sharpen the overall image, eliminate noise, or focus on an imaged object.  
  
> [!TIP]
>  A filter is a transfer function that takes an input signal and creates an output signal based on the filter characteristics. For more general information about the user of filters in digital signal processing, see [Filter](data-transformation-filter.md).  
  
 After you have defined a digital signal processing filter, you can apply the filter to data by connecting a dataset and the filter to the [Apply Filter](apply-filter.md) module. You can also save the filter for re-use with similar datasets.  
  
## How to Configure a FIR Filter  
  
1.  Add the **FIR Filter** module to your experiment.  
  
2.  For **Order**, type an integer value that defines the number of active elements used to affect the filter's response. The *order* of the filter represents the length of the filter window.  
  
     For a FIR filter, the minimum order  is 4.  
  
3.  For **Window**, select the shape of the data to which the filter will be applied. Azure Machine Learning supports the following types of windowing functions for use in finite impulse response filters:  
  
     **Hamming**  
     The *generalized Hamming window* provides a type of weighted averaging, which is commonly used in image processing and computer vision.  
  
     **Blackman**  
     A *Blackman window* applies a smoothly tapered curve function to the signal. The Blackman window has better stopband attenuation than other window types.  
  
     **Rectangular**  
     A *rectangular window* applies a consistent value inside the specified interval and applies no value elsewhere. The simplest rectangular window might replace *n* values in a data sequence with zeros, which makes it appear as though the signal suddenly turns on and off.  
  
     A rectangular window is also known as a *boxcar* or *Dirichlet window*.  
  
     **Triangular**  
     A triangular window applies filter coefficients in a step-wise fashion. The current value appears at the peak of the triangle, and then it declines with preceding or following values.  
  
     **None**  
     In some applications it is preferable not to use any windowing functions. For example, if the signal you are analyzing already represents a window or burst, applying a window function could deteriorate the signal-to-noise ratio.  
  
4.  For **Filter type**, select an option that defines how the filter will affect values. You can specify that the filter exclude the target values, alter the values, reject the values, or pass them through.  
  
     **Lowpass**  
     Removes high-frequency data from a signal, such as high-frequency noise and data peaks. This filter type has a smoothing effect on the data.  
  
     **Highpass**  
     Removes low frequency data from a signal, such as a bias or offset. This filter type preserves sudden changes and peaks in a signal.  
  
     **Bandpass**  
     Preserves the data from a signal with frequency characteristics at the intersection between the highpass and lowpass filters. This filter type is good at removing a bias and smoothing a signal.  
  
     Bandpass filters are created by combining a highpass and a lowpass filter. The highpass filter cutoff frequency represents the lower cutoff, and the lowpass filter frequency represents the higher cutoff.  
  
     **Bandstop**  
     Removes data from a signal with frequency characteristics that are rejected by the low pass and the highpass filters. This filter type is good at preserving the signal bias and sudden changes.  
  
5.  Depending on the type of filter you chose, set one or more cutoff values.  
  
     Use the **High cutoff**  and **Low cutoff**  options to define an upper and/or a lower threshold for values. One or both of these options are required to specify which values are rejected or passed through.  
  
    -   A **bandstop** or **bandpass** filter requires that you set both high and low cutoff values.  
  
    -   Other filter types, such as the **lowpass** filter, require that you set only the low cutoff value.  
  
6.  Select the **Scale** option if scaling should be applied to coefficients; otherwise leave blank.  
  
7.  Connect the filter to [Apply Filter](apply-filter.md), and connect a dataset.  
  
     Use the column selector to specify which columns the filter should be applied to. By default, the [Apply Filter](apply-filter.md) module will use the filter for all selected numeric columns.  
  
8.  Run the experiment.  
  
     Note that the **FIR Filter** module does not provide the option to create an indicator column. Column values are always transformed in place.  
  
## Examples  
 For examples of how filters are used in machine learning, see this experiment in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Filters](http://go.microsoft.com/fwlink/?LinkId=525732) experiment demonstrates all filter types. The example uses an engineered waveform dataset to more easily illustrate the effects of the different filters.  
  
##  <a name="bkmk_Notes"></a> Technical Notes  
 FIR filters have these characteristics:  
  
-   FIR filters do not have feedback; that is, they use the previous filter outputs.  
  
-   FIR filters are more stable, because the impulse response will always return to 0.  
  
-   FIR filters require a higher order to achieve the same selectivity as infinite impulse response (IIR) filters.  
  
-   Like other filters, the FIR filter can be designed with a specific cutoff frequency that preserves or rejects frequencies that compose the signal.  
  
### Calculating Coefficients over the Filter Window  
 The window type determines the trade-off between selectivity (width of the transition band in which frequencies are neither fully accepted nor rejected) and suppression (the total attenuation of frequencies to be rejected).  
  
 The windowing function is applied to the ideal filter response to force the frequency response to zero outside of the window. Coefficients are selected by sampling the frequency response within the window.  
  
 The number of coefficients returned by the **FIR Filter** module is equal to the filter order plus one. The coefficient values are determined by filter parameters and by the windowing method, and are symmetric to guarantee a linear phase response  
  
 See the [Technical Notes](#bkmk_Notes) section for an example of the trade-offs between these characteristics.  
  
###  <a name="CoefficientsScaling"></a> Scaling of Coefficients  
 The **FIR Filter** module returns filter coefficients, or tap weights, for the created filter.  
  
 The coefficients are determined by the filter, based on the parameters you enter (such as the order). If you want to specify custom coefficients, use the [User-Defined Filter](user-defined-filter.md) module.  
  
 When **Scale** is set to **True**, filter coefficients will be normalized, such that the magnitude response of the filter at the center frequency of the passband is 0. The implementation of normalization in Azure Machine Learning Studio is the same as in the **fir1** function in MATLAB.  
  
 Typically, in the window design method, you design an ideal infinite impulse response (IIR) filter. The window function is applied to the waveform in the time domain, and multiplies the infinite impulse response by the window function. This results in the frequency response of the IIR filter being convolved with the frequency response of the window function. However, in the case of FIR filters, the input and filter coefficients (or tap weights) are convolved as follows when applying the filter:  
  
 y=b*x  
  
 Let n be the length of the input signal and m be the number of taps.  
  
 Then *y* j          =∑             m                       i=1          *b* i          *x* j−(i−1)          *j*=1..*n* where the values xj-(i-1)=0 if j-(i-1) < 1.  
  
###  <a name="Example"></a> Selectivity and Stop Band Attenuation  
 The following table compares selectivity with stop band attenuation for a FIR filter with length *n* by using different windowing methods:  
  
|Window Type|Transition Region|Minimum Stopband Attenuation|  
|-----------------|-----------------------|----------------------------------|  
|Rectangular|0.041n|21 dB|  
|Triangle|0.11n|26 dB|  
|Hann|0.12n|44 dB|  
|Hamming|0.23n|53 dB|  
|Blackman|0.2n|75 dB|  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Order|>=4|Integer|5|Specify the filter order|  
|Window|Any|WindowType||Specify the type of window to apply|  
|Filter type|Any|FilterType|LowPass|Select the type of filter to create|  
|Low cutoff|[double.Epsilon;.9999999]|Float|0.3|Set the low cutoff frequency|  
|High cutoff|[double.Epsilon;.9999999]|Float|0.7|Set the high cutoff frequency|  
|Scale|Any|Boolean|True|If true, filter coefficients will be normalized|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
  
##  <a name="exceptions"></a> Exception  
 For a list of all exceptions, see [Machine Learning REST API Error Codes](http://msdn.microsoft.com/library/0eccb2eb-27a1-407e-88a9-2092dba847e0).  
  
|Exception|Description|  
|---------------|-----------------|  
|NotInRangeValue|Exception occurs if parameter is not in range.|  
  
## See Also  
 [Filter](data-transformation-filter.md)   
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)