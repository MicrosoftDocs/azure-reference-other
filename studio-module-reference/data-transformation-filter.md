---
title: "Data Transformation - Filter | Microsoft Docs"
ms.custom: ""
ms.date: 10/06/2017
ms.reviewer: ""
ms.service: "machine-learning"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 529b4991-8a7f-4e12-8f36-51f9faca4383
caps.latest.revision: 20
author: "jeannt"
ms.author: "jeannt"
manager: "jhubbard"
---
# Data Transformation - Filter
This article describes how you can use the filter modules in Azure Machine Learning Studio to transform digital data. 

## What is filtering?

Typically, filters are applied to digital data during the data processing or preprocessing stages, to enhance the clarity of the signal used for machine learning. For example, the filter modules in Azure Machine Learning Studio can be used for these processing tasks:  
  
-   Analyze interference or artifacts in telemetry signals.  
  
-   Cleanup of waveforms used for speech recognition.  
  
-   Detect trends or remove seasonal effects in noisy sales or economic data.  

The modules in this group of tools for Azure Machine Learning Studio are based on filters developed for signal processing technology.  These modules provide easy configuration of filters, using well researched algorithms, to mathematically transform waveform data. You can also create a custom filter if you have already determined the correct coefficients to apply to your data.  
 
### Related tasks  

The word "filter" can be used to mean many different things. If you need to do tasks such as excluding data from a dataset on a row by row basis, removing missing values, or reducing the size of a dataset, use these modules instead:  

+ [Clean Missing Data](clean-missing-data.md) - Remove missing values or replace missing values with placeholders.  
+ [Partition and Sample](partition-and-sample.md) - Divide or filter your dataset by criteria such as a range of dates, a specific value, or regular expressions.  
+ [Clip Values](clip-values.md) - Set a range of values and keep only the values within that range.  
  
### The role of filters in digital signal processing

Just as a filter can be attached to a camera to compensate for lighting or create special effects, you can apply a filter to the data used for machine learning, to improve the clarity of a signal, to capture interesting characteristics, or to reduce noise.  
  
 The ideal filter would eliminate all noise and have uniform sensitivity for the desired signal, but designing even a pretty good filter might take many iterations or combinations of techniques. If you succeed in designing an effective filter, consider saving the filter so that you can reuse it when transforming new data.  
 
 In general, filtering is based on the principles of *waveform analysis*. When you design a filter, you look for ways to suppress or amplify parts of the signal, to expose underlying trends, reduce noise and interference, or to identify data values that otherwise might not be perceived.  
  
 Various techniques are applied to decompose the individual trends or waveform components that create the actual data values. The series of values (whether that is an econometric series or the composite frequencies of audio signals) can be analyzed by using trigonometric functions to identify and isolate individual wave forms. Filters can then be applied to these wave forms to eliminate noise, amplify some waves, or remove targeted components.  
  
 When filtering is applied to a noisy series to isolate different components, you can specify which frequencies to remove or strengthen by specifying the band of frequencies to work with. 

The following type of filters are supported in Azure Machine Learning Studio:
  
-   **Filters based on waveform decomposition**, such as finite impulse response (FIR) and infinite impulse response (IIR) filters. These filters work by removing specific components from an overall series, which lets you view and investigate the simplified waveform.  
  
-   **Filters based on moving averages or median values**. These filters smooth out variations in a data series by averaging across windows of time. The windows can be fixed or sliding, and they can have different shapes. For example, a triangular window peaks at the current data point (weights the current value stronger) and tails off before and after the data point (weights preceding and following values less strongly).  
  
-   **User-defined or custom filters**. If you already know the transformations that should be applied to a data series, you can create a user-defined filter and provide the numeric coefficients that are applied to transform the data series. A custom filter can emulate a FIR or IIR filter but you have more control over the values to apply at each point in the series.  
  
###  <a name="subsection3"></a> Filter terminology  

 The following are some simple definitions of terms that are used in the parameters and properties of filters.  
  
-   **Passband**: The range of frequencies that can pass through a filter without being attenuated or weakened.  
  
-   **Stopband**: A range of frequencies between specified limits, through which signals are not passed. You define the stopband by setting cut-off frequencies.  
  
-   **High pass**: Let only high frequencies through.  
  
-   **Low pass**: Accept only frequencies below a specified cut-off value.  
  
-   **Corner**: The corner frequency defines the boundary between the stopband and passband frequencies. Typically, you have the option to decide whether the corner is included in or excluded from the band. A first-order filter causes gradual attenuation until the corner frequency and exponential attenuation after that. Higher-order filters (such as Butterworth and Chebyshev filters) have steeper slopes after the corner frequency and attenuate the values in the stopband much more rapidly and fully.  
  
-   **Bandstop filter** (also called a **band reject** filter and a **notch** filter): Has only one stopband, which you define by specifying two frequencies: the high cut-off and low cut-off. A **bandpass** filter typically has two stopbands, one on either side of the desired component.  
  
-   **Ripple**: A small unwanted variation that occurs periodically. In Azure Machine Learning, you can specify the amount of ripple to tolerate as part of the parameters in the IIR filter design.  
  
> [!TIP]
> Need more information? If you are new to digital signal processing, this ham radio education site provides definitions and helpful visual aids that explain basic terminology and concepts: 
> 
> [An Introduction to Digital Signal Processing](http://www.hamradioschool.com/an-introduction-to-digital-signal-processing-dsp/)   
  
##  <a name="modules"></a> List of Modules  
 The modules in the Filter category include:  
  
|Module|Description|  
|------------|-----------------|  
|[Apply Filter](apply-filter.md)|Applies a filter to specified columns of a dataset|  
|[FIR Filter](fir-filter.md)|Creates a finite impulse response filter for signal processing|  
|[IIR Filter](iir-filter.md)|Creates an infinite impulse response filter for signal processing|  
|[Median Filter](median-filter.md)|Creates a median filter used to smooth data for trend analysis|  
|[Moving Average Filter](moving-average-filter.md)|Creates a moving average filter that smooths data for trend analysis|  
|[Threshold Filter](threshold-filter.md)|Creates a threshold filter that constrains values|  
|[User-Defined Filter](user-defined-filter.md)|Creates a custom finite or infinite impulse response filter|  
  
## See Also  
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)