---
title: "Clip Values | Microsoft Docs"
titleSuffix: ML Studio (classic) - Azure
description: Learn how to use the Clip Values module to identify and optionally replace data values that are above or below a specified threshold.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs
manager: cgronlun
---
# Clip Values

*Detects outliers and clips or replaces their values*  

Category: [Data Transformation / Scale and Reduce](data-transformation-scale-and-reduce.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview

This article describes how to use the **Clip Values** module in Azure Machine Learning Studio (classic), to identify and optionally replace data values that are above or below a specified threshold. This is useful when you want to remove outliers or replace them with a mean, a constant, or other substitute value.  

You connect the module to a dataset that has the numbers you want to clip, choose the columns to work with, and then set a threshold or range of values, and a replacement method. The module can output either just the results, or the changed values appended to the original dataset.

## How to configure Clip Values

Before you begin, identify the columns you want to clip, and the method to use. We recommend that you test any clipping method on a small subset of data first.

The module applies the same criteria and replacement method to **all** columns that you include in the selection. Therefore, be sure to exclude columns that you don't want to change.

If you need to apply clipping methods or different criteria to some columns, you must use a new instance of **Clip Values** for each set of similar columns.

1.  Add the **Clip Values** module to your experiment and connect it to the dataset you want to modify. You can find this module under **Data Transformation**, in the **Scale and Reduce** category. 
  
2.  In **List of columns**, use the Column Selector to choose the columns to which **Clip Values** will be applied.  
  
3.  For **Set of thresholds**, choose one of the following options from the dropdown list. These options determine how you set the upper and lower boundaries for acceptable values vs. values that must be clipped.  
  
    - **ClipPeaks**: When you clip values by peaks, you specify only an upper boundary. Values greater than that boundary value are replaced or removed.
  
    -  **ClipSubpeaks**: When you clip values by sub-peaks, you specify only a lower boundary. Values that are less than that boundary value are replaced or removed.  
  
    - **ClipPeaksAndSubpeaks**: When you clip values by peaks and sub-peaks, you can specify both the upper and lower boundaries. Values that are outside that range are replaced or removed. Values that match the boundary values are not changed.
  
4.  Depending on your selection in the preceding step, you can set the following threshold values: 

    + **Lower threshold**: Displayed only if you choose **ClipSubPeaks**
    + **Upper threshold**: Displayed only if you choose **ClipPeaks**
    + **Threshold**: Displayed only if you choose **ClipPeaksAndSubPeaks**

    For each threshold type, choose either **Constant** or **Percentile**.

5. If you select **Constant**, type the maximum or minimum value in the text box. For example, assume that you know the value 999 was used as a placeholder value. You could choose **Constant** for the upper threshold, and type 999 in **Constant value of upper threshold**.
  
6. If you choose **Percentile**, you constrain the column values to a percentile range. 

    For example, assume you want to keep only the values in the 10-80 percentile range, and replace all others. You would choose **Percentile**, and then type 10 for **Percentile value of lower threshold**, and type 80 for **Percentile value of upper threshold**. 

    See the section on [percentiles](#bkmk_Percentiles) for some examples of how to use percentile ranges.  
  
5.  Define a substitute value.

    Numbers that exactly match the boundaries you just specified are considered to be inside the allowed range of values, and thus are not replaced or removed. All numbers that fall outside the specified range are replaced with the substitute value. 
  
    + **Substitute value for peaks**: Defines the value to substitute for all column values that are greater than the specified threshold.  
    + **Substitute value for subpeaks**: Defines the value to use as a substitute for all column values that are less than the specified threshold.  
    + If you use the **ClipPeaksAndSubpeaks** option, you can specify separate replacement values for the upper and lower clipped values.  

    The following replacement values are supported:  
  
    -   **Threshold**: Replaces clipped values with the specified threshold value.  
  
    -   **Mean**: Replaces clipped values with the mean of the column values. The mean is computed before values are clipped.  
  
    -   **Median**: Replaces clipped values with the median of the column values. The median is computed before values are clipped.   
  
    -   **Missing**. Replaces clipped values with the missing (empty) value.  
  
6.  **Add indicator columns**: Select this option if you want to generate a new column that tells you whether or not the specified clipping operation applied to the data in that row. This option is particularly handy when you are testing a new set of clipping and substitution values.  
  
7. **Overwrite flag**: Indicate how you want the new values to be generated. By default, **Clip Values** constructs a new column with the peak values clipped to the desired threshold. New values overwrite the original column.  
  
    To keep the original column and add a new column with the clipped values, deselect this option.  
  
8.  Run the experiment.  
  
    Right-click the output of the **Clip Values** module and select **Visualize** to review the values and make sure the clipping operation met your expectations.  

## Examples  

To see how this module is used in machine learning experiments, see the [Azure AI Gallery](https://gallery.azure.ai/):  

+ [Forest Fire outliers](https://gallery.azure.ai/Experiment/Forest-Fires-Outliers-1): This example from the EdX couse in data science demonstrates clipping methods using the Forest Fires sample dataset.

###  <a name="bkmk_Percentiles"></a> Clipping using percentiles

To understand how clipping by percentiles works, consider a dataset with 10 rows, which have one instance each of the values 1-10.  
  
+ If you are using percentile as the upper threshold, at the value for the 90th percentile, 90 percent of all values in the dataset must be less than that value.  
  
+ If you are using percentile as the lower threshold, at the value for the 10th percentile, 10 percent of all values in the dataset must be less than that value.  
  
1.  For **Set of thresholds**, choose **ClipPeaksAndSubPeaks**.  
  
2.  For **Upper threshold**, choose **Percentile**, and for **Percentile number**, type 90.  
  
3.  For **Upper substitute value**, choose **Missing Value**.  
  
4.  For **Lower threshold**, choose **Percentile**, and for **Percentile number**, type 10.  
  
5.  For **Lower substitute value**, choose **Missing Value**.  
  
6.  Deselect the option **Overwrite flag**, and select the option, **Add indicator column**.  
  
Now try the same experiment using 60 as the upper percentile threshold and 30 as the lower percentile threshold, and use the threshold value as the replacement value. The following table compares these two results:  
  
1.  Replace with missing; Upper threshold = 90; Lower threshold = 10  
  
2.  Replace with threshold; Upper percentile = 60; Lower percentile = 30  
  
|Original data|Replace with missing|Replace with threshold|  
|-------------------|--------------------------|----------------------------|  
|1<br /><br /> 2<br /><br /> 3<br /><br /> 4<br /><br /> 5<br /><br /> 6<br /><br /> 7<br /><br /> 8<br /><br /> 9<br /><br /> 10|TRUE<br /><br /> TRUE<br /><br /> 3, FALSE<br /><br /> 4, FALSE<br /><br /> 5, FALSE<br /><br /> 6, FALSE<br /><br /> 7, FALSE<br /><br /> 8, FALSE<br /><br /> 9, FALSE<br /><br /> TRUE|4, TRUE<br /><br /> 4, TRUE<br /><br /> 4, TRUE<br /><br /> 4, TRUE<br /><br /> 5, FALSE<br /><br /> 6, FALSE<br /><br /> 7, TRUE<br /><br /> 7, TRUE<br /><br /> 7, TRUE<br /><br /> 7, TRUE|  
  
## Technical notes  
  
-   You can use **Clip Values** only on columns containing numbers or date/time values.  
  
-   If you include columns that have text or categorical data, the columns will be skipped.  
  
-   Missing values are ignored when the mean or median value is computed for a column.  
  
-   **Clip Values** does not support ordinal data.  
  
-   Missing values are not altered when they are propagated to the output dataset.  The column indicating clipped values always contains FALSE for missing values.  
  
## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
## Module parameters  

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Add indicator columns|TRUE/FALSE|Boolean|FALSE|Whether to add indicator for clipping of a value is done|  
|Constant value for lower threshold|any|Float|-1|Value below which the subpeaks will be clipped|  
|Constant value for upper threshold|any|Float|1|Value above which the peaks will be clipped|  
|Constant value of lower threshold|any|Float|-1|Value below which the subpeaks are clipped|  
|Constant value of upper threshold|>=1|Float|1|Value above which the peaks are clipped|  
|List of columns||ColumnSelection||List of columns to clip|  
|Lower substitute value|Threshold<br /><br /> Mean<br /><br /> Median<br /><br /> Missing|SubstituteValues|Threshold|The value used for clipping subpeaks|  
|Lower threshold|Constant<br /><br /> Percentile|Threshold Mode|Constant|Value below which the subpeaks will be clipped mode|  
|Overwrite flag|TRUE/FALSE|Boolean|TRUE|Whether clipped data column(s) must overwrite input data column(s)|  
|Percentile number for lower threshold|[1;99]|Integer|1|Percentile number below which the subpeaks will be clipped|  
|Percentile number for upper threshold|[1;99]|Integer|99|Percentile number above which the peaks will be clipped|  
|Percentile number of lower threshold|[1;99]|Integer|1|Percentile number below which the subpeaks are clipped|  
|Percentile number of upper threshold|[1;99]|Integer|99|Percentile number above which the peaks are clipped|  
|Set of thresholds|ClipPeaks<br /><br /> ClipSubPeaks<br /><br /> ClipPeaksAndSubPeaks|Threshold Set|ClipPeaks|Specifies type of threshold to use|  
|Substitute value for peaks|Threshold<br /><br /> Mean<br /><br /> Median<br /><br /> Missing|SubstituteValues|Threshold|The value used during clipping peaks|  
|Substitute value for subpeaks|Threshold<br /><br /> Mean<br /><br /> Median<br /><br /> Missing|SubstituteValues|Threshold|The value used during clipping subpeaks|  
|Threshold|Constant<br /><br /> Percentile|Threshold Mode|Constant|Value above and below which the peaks will be clipped mode|  
|Upper substitute value|Threshold<br /><br /> Mean<br /><br /> Median<br /><br /> Missing|Threshold|Threshold|The value used for clipping peaks|  
|Upper threshold|Constant<br /><br /> Percentile|Threshold Mode|Constant|Value above which the peaks will be clipped mode|  
  
## Outputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Dataset with clipped columns|  

## Exceptions  

|Exception|Description|  
|---------------|-----------------|  
|[Error 0011](errors/error-0011.md)|Exception occurs if passed column set argument does not apply to any of dataset columns.|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have type unsupported by current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](https://docs.microsoft.com/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Scale and Reduce](data-transformation-scale-and-reduce.md)   
 [A-Z Module List](a-z-module-list.md)
