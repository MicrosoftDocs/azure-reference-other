---
title: "User-Defined Filter | Microsoft Docs"
ms.custom: ""
ms.date: 06/21/2016
ms.prod: ""
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 53f113fe-2e9d-45dd-a421-cdd7ada0567b
caps.latest.revision: 19
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# User-Defined Filter
*Creates a custom finite or infinite impulse response filter*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  
  
##  <a name="Remarks"></a> Module Overview  
 You can use the **User-Defined Filter** module to define a custom filter by using a finite impulse response (FIR) filter or an infinite impulse response (IIR) filter with coefficients that you specify.  
  
 This module is particularly useful for applying a set of previously derived filter coefficients to your data.  
  
 After you have defined a filter that meets your needs, you can apply the filter to data by connecting a dataset and the filter to the [Apply Filter](apply-filter.md) module.  
  
## How to Configure a Custom Filter  
 To define a custom filter:  
  
1.  Define the general type of filter: FIR filter, or IIR filter.  
  
2.  Provide the coefficients.  
  
     The requirements for the coefficients  differ depending on whether you choose a FIR filter or an IIR filter.  
  
    -   For a FIR filter, you specify a vector of feed-forward coefficients. The length of the vector determines the filter's order.  
  
         A FIR filter is effectively a moving average, so the configuration values apply a moving average to filter a data sequence.  
  
    -   For an IIR filter, you apply custom feed-forward and feed-backward coefficients. The following examples demonstrate some configuration values.  
  
 See the [Examples](#bkmk_Examples) section for links to experiments that use the filter modules.  
  
##  <a name="SubSection1a"></a> FIR Filter Example: Exponential Weighted Moving Average  
 For an exponentially weighted moving average, all coefficients are less than one and the sum of all coefficients equals one. Therefore, the variance of the weighted average will always be less than the input values.  
  
 For example, for a FIR filter to approximate an exponentially weighted moving average (WMA), you would supply a comma-separated list of coefficients for the value for the feed-forward parameter:  
  
 `0.01818182,             0.03636364,             0.05454545,             0.07272727,             0.09090909,             0.10909091,             0.12727273,             0.14545455,             0.16363636,             0.18181818`  
  
##  <a name="SubSection1b"></a> FIR Filter Example: Exponential Weighted Moving Average (Deslauriers-Dubuc Interpolation)  
 This FIR filter approximates a triangularly weighted moving average (WMA).  
  
 You define the coefficients by supplying a comma-separated series of values for the feed-forward parameters, such as these:  
  
 `0.0625,             0.0625             0.2500,             0.3750,             0.2500,             0.0625`  
  
 The values used in this custom FIR filter represent a vector of feed-forward coefficients obtained by using the Deslauriers-Dubuc method of finite sequencing. For more information, see [Dubuc-Deslauriers Subdivision for Finite Sequences and Interpolation Wavelets on an Interval-](http://dip.sun.ac.za/~herbst/research/publications/subdiv.pdf).  
  
##  <a name="SubSection2"></a> IIR Filter Example: Notch Filter  
 A good example of an application for a user-defined IIR filter is to define a *notch filter*, also called a *bandstop filter*.  
  
 The desired notch filter attenuates a -3dB rejection band, *fb*, centered at a notch frequency, fn, with a sampling frequency, fs:  
  
 The digital notch filter can be represented by:  
  
 ![custom notch filter example 1](media/aml-digitalnotchfilter.PNG "aml_digitalnotchfilter")  
  
 Where:  
  
 ![custom notch filter](media/aml-usernotchfilter4.png)  
  
 From this form, we can get the feed-forward coefficient:  
  
 ![feed forward coefficient for custom notch filter](media/aml-digitalnotchfilter-ffcoefficient.PNG "aml_digitalnotchfilter-ffcoefficient")  
  
 And the feed-backward coefficients as:  
  
 ![feed back coefficient for custom notch filter](media/aml-digitalnotchfilter-fbcoefficient.PNG "aml_digitalnotchfilter-fbcoefficient")  
  
## IIR Filter: Notch Filter 2  
 Following is an example of a notch filter with a notch frequency of f n =1250 Hz and a -3 dB rejection band of fb =100 Hz, with sampling frequency of fs=10 kHz.  
  
 ![formula for notch filter example 2&#45;1](media/aml-notchfilterexample2-1.PNG "aml_notchfilterexample2-1")  
  
 If we use:  
  
 ![formulas 2 for notch filter example 2](media/aml-notchfilterexample2-2.PNG "aml_notchfilterexample2-2")  
  
 We get:  
  
 a             2 = 0.93906244  
  
 a             1 = 1.3711242  
  
 From this, the feed-forward (b) and feed-backward (a) coefficients are:  
  
 b= `1.9390624, -2.7422484, 1.9390624`  
  
 a= `1, -1.3711242, 0.9390624`  
  
##  <a name="bkmk_Examples"></a> Examples  
 For more examples of how filters are used in machine learning, see these experiments in the [Model Gallery](https://gallery.cortanaintelligence.com/):  
  
-   The [Filters](http://go.microsoft.com/fwlink/?LinkId=525732) experiment demonstrates all filter types. The example uses an engineered waveform dataset to more easily illustrate the effects of the different filters.  
  
##  <a name="parameters"></a> Module Parameters  
  
|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Type of filter|any|ImpulseResponse||Specify the type of filter to customize|  
|Forward|any|String|"1.0"|Type a series of feed-forward coefficients|  
|Backward|any|String|"1.0"|Type a series of feed-backward filter coefficients|  
  
##  <a name="Outputs"></a> Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  
  
##  <a name="exceptions"></a> Exception  
 For a list of all exceptions, see [Machine Learning REST API Error Codes](http://msdn.microsoft.com/library/0eccb2eb-27a1-407e-88a9-2092dba847e0).  
  
|Exception|Description|  
|---------------|-----------------|  
|ParameterParsing|An exception occurs if one or more parameters could not be parsed or converted from the specified type into the type that is required by the target method.|  
  
## See Also  
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)