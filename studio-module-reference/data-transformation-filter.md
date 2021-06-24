---
title: "ML Studio (classic): Data Transformation: Filter - Azure"
description: "Learn how to use the filter modules to transform digital data."
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Data Transformation - Filter

This article describes how you can use the filter modules in Machine Learning Studio (classic) to transform digital data.  The modules in this group of tools for Machine Learning Studio (classic) are based on filters that were developed for digital signal processing technology.

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

Filters typically are applied to data in the data processing stage or the preprocessing stage. Filters enhance the clarity of the signal that's used for machine learning. For example, you can use the filter modules in Machine Learning Studio (classic) for these processing tasks:

-   Clean up waveforms that are used for speech recognition.
-   Detect trends or remove seasonal effects in noisy sales or economic data.
-   Analyze patterns or artifacts in telemetry signals.

These modules provide easy configuration of filters by using well-researched algorithms to mathematically transform waveform data. You can also create a custom filter if you have already determined the correct coefficients to apply to your data.

## Related tasks

If you need to do tasks such as excluding data from a dataset on a row-by-row basis, removing missing values, or reducing the size of a dataset, use these modules instead:

- [Clean Missing Data](clean-missing-data.md): Remove missing values, or replace missing values with placeholders.
- [Partition and Sample](partition-and-sample.md): Divide or filter your dataset by using criteria such as a range of dates, a specific value, or regular expressions.
- [Clip Values](clip-values.md): Set a range of values, and keep only the values within that range.

## Filters in digital signal processing

Just like you can attach a filter to a camera to compensate for lighting or to create special effects, you can apply a filter to the data that you use for machine learning. Filters can help improve the clarity of a signal, capture interesting characteristics, or reduce noise.

The ideal filter would eliminate all noise and have uniform sensitivity for the desired signal. But, designing even a pretty good filter might take many iterations or combinations of techniques. If you succeed in designing an effective filter, consider saving the filter so that you can reuse it when you transform new data.

In general, filtering is based on the principles of *waveform analysis*. When you design a filter, you look for ways to suppress or amplify parts of the signal, to expose underlying trends, to reduce noise and interference, or to identify data values that otherwise might not be perceived.

Various techniques are applied to decompose individual trends or waveform components that create actual data values. The series of values can be analyzed by using trigonometric functions to identify and isolate individual waveforms. (This is true whether it's an econometric series or the composite frequencies of audio signals.) Filters can then be applied to these waveforms to eliminate noise, amplify some waves, or remove targeted components.

When filtering is applied to a noisy series to isolate different components, you can specify which frequencies to remove or strengthen by specifying the band of frequencies to work with.

### Digital filters in Machine Learning Studio (classic)

The following types of filters are supported in Machine Learning Studio (classic):
  
-   **Filters based on waveform decomposition**. Examples include finite impulse response (FIR) and infinite impulse response (IIR) filters. These filters work by removing specific components from an overall series. You can then view and investigate the simplified waveform.  
-   **Filters based on moving averages or median values**. These filters smooth out variations in a data series by averaging across windows of time. The windows can be fixed or sliding, and can have different shapes. For example, a triangular window peaks at the current data point (weights the current value stronger) and tails off before and after the data point (weights preceding and following values less strongly).  
-   **User-defined or custom filters**. If you already know the transformations that should be applied to a data series, you can create a user-defined filter. You provide the numeric coefficients that are applied to transform the data series. A custom filter can emulate an FIR or IIR filter. However, with a custom filter, you have more control over the values to apply at each point in the series.
  
###  Filter terminology

The following list includes simple definitions of terms that are used in the parameters and properties of filters:
  
-   **Passband**: The range of frequencies that can pass through a filter without being attenuated or weakened.  
-   **Stopband**: A range of frequencies between specified limits through which signals are not passed. You define the stopband by setting cut-off frequencies.  
-   **High pass**: Let only high frequencies through.  
-   **Low pass**: Accept only frequencies below a specified cut-off value.  
-   **Corner**: Defines the boundary between the stopband and passband frequencies. Typically, you have the option to decide whether the corner is included in or excluded from the band. A first-order filter causes gradual attenuation until the corner frequency. After that, the filter causes exponential attenuation. Higher-order filters (such as Butterworth and Chebyshev filters) have steeper slopes after the corner frequency. Higher-order filters attenuate the values in the stopband much more rapidly and fully.  
-   **Bandstop filter** (also called a *band reject* filter or a *notch* filter): Has only one stopband. You define the stopband by specifying two frequencies: the high cut-off frequency and the low cut-off frequency. A *bandpass* filter typically has two stopbands: one on either side of the desired component.  
-   **Ripple**: A small, unwanted variation that occurs periodically. In Machine Learning, you can specify the amount of ripple to tolerate as part of the parameters in the IIR filter design.

> [!TIP]
> Need more information? If you are new to digital signal processing, see [An Introduction to Digital Signal Processing](https://www.hamradioschool.com/an-introduction-to-digital-signal-processing-dsp/). The website provides definitions and helpful visual aids that explain basic terminology and concepts. 
> 
  
## List of modules

The following modules are included in the **Data Transformation - Filter** category:

- [Apply Filter](apply-filter.md): Applies a filter to specified columns of a dataset.
- [FIR Filter](fir-filter.md): Creates an FIR filter for signal processing.
- [IIR Filter](iir-filter.md): Creates an IIR filter for signal processing.
- [Median Filter](median-filter.md): Creates a median filter that's used to smooth data for trend analysis.
- [Moving Average Filter](moving-average-filter.md): Creates a moving average filter that smooths data for trend analysis.
- [Threshold Filter](threshold-filter.md): Creates a threshold filter that constrains values.
- [User-Defined Filter](user-defined-filter.md): Creates a custom FIR or IIR filter.

## See also

- [Data Transformation](data-transformation.md)
- [A-Z module list](a-z-module-list.md)
