---
title: "ML Studio (classic): Threshold Filter - Azure"
description: Learn how to use the Threshold Filter module to define a filter that restricts numeric values to a specified range.
ms.custom: "formulas"
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Threshold Filter
*Creates a threshold filter that constrains values*  
  
 Category: [Data Transformation / Filter](data-transformation-filter.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview

This article describes how to use the **Threshold Filter** module in Machine Learning Studio (classic), to define a filter that restricts numeric values to a specified range.

Threshold filters are commonly used in digital signal processing. A threshold filter examines each value of the input dataset and changes all values that do not meet the boundary conditions. You typically would use this type of filter for the following applications:  

+ Replace all negatively signed measurements with a value of zero.
+ Convert a gray-scale image to black and white areas by defining a numerical boundary value for all pixels.  

After you have defined a filter that meets your needs, you can apply the filter to data by connecting a dataset and the filter to the [Apply Filter](apply-filter.md) module.  

The output of the [Apply Filter](apply-filter.md) module is a dataset containing the selected columns, transformed as specified by the **Threshold Filter** settings.  

Alternatively, if you select the **Indicator** option, instead of returning the filter values, a column is returned containing Boolean values that indicates whether the value in each row met the specified filter condition or not. This can be useful when you are testing a new filter.  

> [!TIP]
> Need to filter data from a dataset or remove missing values? Use these modules instead:  
> 
> - [Clean Missing Data](clean-missing-data.md): Use this module to remove missing values or replace missing values with placeholders.  
> - [Partition and Sample](partition-and-sample.md): Use this module to divide or filter your dataset by criteria such as a range of dates, a specific value, or regular expressions.  
> - [Clip Values](clip-values.md): Use this module to set a range and keep only the values within that range.

## How to configure Threshold Filter
  
1.  Add the **Threshold Filter** module to your experiment. You can find this module under **Data Transformation**, in the **Filter** category.
  
2.  For **Type**, specify the type of filter to apply:  
  
    -   **LessThan**: Changes values that are less than the specified level to the boundary level, and passes through all other values.  
  
    -   **GreaterThan**: Changes values that are greater than the specified level to the boundary level, and passes through all other values.  
  
    -   **MagnitudeLessThan**: Changes values less than the specified level to the boundary level but preserves the sign of the original value.  
  
    -   **MagnitudeGreaterThan**: Changes values greater than the specified level to the boundary level but preserves the sign of the original value.  
  
    -   **InRange**: Passes through all values that fall within the specified range, and changes values outside the range to the closest boundary value.  
  
    -   **OutOfRange**: Passes through all values that fall outside the specified range, and changes values inside the range to the closest boundary value.  
  
    -   **InRangeWithStd**: Passes through all values that fall within the specified range of standard deviations, and changes values outside the range to the closest boundary value.  
  
    -   **OutOfRangeWithStd**: Passes through all values that fall outside the specified range of standard deviations, and changes values inside the range to the closest boundary value.  
  
3.  For **Level**, type the boundary value to apply in each type of threshold.  
  
    -   If you select the **LessThan** filter, the number you specify defines the lowest value that can be passed through without replacement.  
  
    -   If you select the **GreaterThan** filter, the number you specify defines the greatest value that can be passed through without replacement.  
  
    -   If you select the **MagnitudeLessThan** filter, type a single positive or negative number for **Level**.  Any value that is less than that value is replaced with the level value.  
  
    -   If you select the **MagnitudeGreaterThan** filter, type a single positive or negative number for **Level**.  Any value that is greater than that value is replaced with the level value.  
  
    -   If you select the filters, **InRange** or**OutOfRange**, specify the upper or lower bounds. For **Lower boundary**, type the lowest number to include in the range. For **Upper boundary**, type the highest number to include in the range.
  
    -   If you chose one of the filter types that uses standard deviations (**InRangeWithStd**, **OutOfRangeWithStd**), you must specify the **Alpha** constant. The values of alpha times the deviation is used to calculate the filter result.  
  
4.  Optionally, select the **Indicator** option to generate a column that only indicates whether the value would be affected by the filter. If you leave **Indicator** unselected, the filter generates the replacement values.  
  
5.  Connect the filter to [Apply Filter](apply-filter.md), and connect a dataset.  
  
     Use the column selector to specify which columns the filter should be applied to. By default, the [Apply Filter](apply-filter.md) module applies the filter transformation to all selected numeric columns.

6. Run the experiment.

    No computations are performed until you connect a dataset to the [Apply Filter](apply-filter.md) module and run the experiment. At that point, the specified transformation is applied to the selected numeric columns.

## Examples

For examples of how filters are used in machine learning, see this experiment in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
-  [Filters](https://go.microsoft.com/fwlink/?LinkId=525732): This experiment demonstrates all filter types, using an engineered waveform dataset.

### Examples of indicator values

The following example assumes that you apply a threshold filter that specifies a range with a lower boundary of 2 and an upper boundary of 4:  

|Value|Indicator|Replace with|  
|-----------|---------------|------------------|  
|1|FALSE|2|  
|2|TRUE|2|  
|3|TRUE|3|  
|4|TRUE|4|  
|5|FALSE|4|  
  
### Examples of magnitude in a filter  

The filter types **MagnitudeLessThan** and **MagnitudeGreaterthan** first evaluate the value against the specified level, and then provide a replacement value that varies depending on the sign of the original values.  
  
### Examples of magnitude filters

The filter types **MagnitudeLessThan** and **MagnitudeGreaterthan** first evaluate the value against the specified level, and then provide a replacement value that varies depending on the sign of the original values. 

For example, the following table shows the results when using a **MagnitudeLessThan** filter with values of 5 and -5.

|Source value|Level|New value|  
|-----|-----|-----|  
|3.07|5|5<br /><br /> Value is less than 5; therefore value is replaced with **Level**|  
|3.07|*-5*|3.07<br /><br /> Value is not less than -5; therefore value is not replaced|  
|-3.93|5|-5<br /><br /> Value is less than 5; therefore value is replaced with **Level** but sign of original value is preserved|  
|-3.93|*-5*|-3.93<br /><br /> Value is not less than -5; therefore value is not replaced|  
|5.75|5|5.75<br /><br /> Value is not less than -5; therefore value is not replaced|  
|-5.75|*-5*|-5.75<br /><br /> Value is not less than -5; therefore value is not replaced|  

##  Technical notes

This section contains implementation details, tips, and answers to frequently asked questions.

### Implementation details

The **Threshold Filter** module uses the following methods to define threshold values, depending on the filter type:  
  
-   **LessThan**: The less-than mode is defined as:  
  
     ![calculating threshold for less than filter](media/aml-threshold-lessthan.png "AML_threshold-lessthan")  
  
     **MagnitudeLessThan**: The less-than-magnitude mode is defined as:  
  
     ![threshold for magnitude less than filter](media/aml-threshold-magnitudelessthan.png "AML_threshold-magnitudelessthan")  
  
     For complex inputs, the magnitude of each element is restricted as shown by this formula:  
  
     ![calculating threshold for less than filter complex](media/aml-threshold-greaterthancomplex.png "AML_threshold-greaterthancomplex")  
  
-   **MagnitudeGreaterThan**: The greater than magnitude mode is defined as:  
  
     ![calculating threshold for greater than filter](media/aml-threshold-greaterthan.png "AML_threshold-greaterthan")  
  
     For complex inputs, the magnitude of each element is restricted as shown by this formula:  
  
     ![calculating threshold for less than filter complex](media/aml-threshold-greaterthancomplex.png "AML_threshold-greaterthancomplex")  

##  Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Type|Any|ThresholdType|LessThan|Select the threshold method to use|  
|Indicator|Any|Boolean|false|Select this option to return a column that contains a True/False indication of whether the value met the filter condition, rather than the filtered values.|  
|Level|Any|Float|0.0|Set the replacement value|  
|Lower boundary|Any|Float|-1.0|Specify the lower boundary of the range|  
|Upper boundary|Any|Float|1.0|Specify the upper boundary of the range|  
|Alpha|Any|Float|3.0|Use this value, multiplied by the calculated standard deviation, as the threshold|  
  
##  Output  
  
|Name|Type|Description|  
|----------|----------|-----------------|  
|Filter|[IFilter interface](ifilter-interface.md)|Filter implementation|  

## See also  
 [Filter](data-transformation-filter.md)   
 [Apply Filter](apply-filter.md)   
 [A-Z Module List](a-z-module-list.md)
