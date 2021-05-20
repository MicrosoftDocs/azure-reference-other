---
title: "ML Studio (classic): Compute Elementary Statistics - Azure"
description: Learn how to use the Compute Elementary Statistics module to generate key statistics such as mean, standard deviation, and the range of values for each of the selected columns.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Compute Elementary Statistics

*Calculates specified summary statistics for selected dataset columns*  

Category: [Statistical Functions](statistical-functions.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]

## Module overview  

This article describes how to use the [Compute Elementary Statistics](compute-elementary-statistics.md) module in Azure Machine Learning Studio (classic), to generate a summary report for your dataset that lists key statistics such as mean, standard deviation, and the range of values for each of the selected columns.  
  
 This report is useful for analyzing the central tendency, dispersion, and shape of data.  
  
## How to configure Compute Elementary Statistics
  
1.  Add the [Compute Elementary Statistics](compute-elementary-statistics.md) module to your experiment. You can find this module in the [Statistical Functions](statistical-functions.md) category in Azure Machine Learning Studio (classic).

2. Connect a dataset that contains the columns you want to analyze.
 
3. Click the **Method** dropdown list, and choose the type of value that you want to calculate for each column.  
  
     See the [Supported Statistics](#bkmk_SupportedStats) section for a full list of available statistics and what they mean.  
  
2.  By default, the value you selected in **Method** dropdown list will be calculated for all columns in the dataset that have a numeric data type. If any column has values that prevent the value from being calculated, an error will be raised and the report will not be created. 

    To avoid this error, use the column selector to pick the numeric columns for which you want a report. All columns that you choose must be numeric.

3.  Run the experiment.  

### Results

The generated report includes the name of each column and the statistic that was calculated.  For example, the following table shows statistics generated for the **mpg** column.    
  
|DeviationSquared(mpg)|Max(mpg)|Min(mpg)|  
|-----------------------------|----------------|----------------|  
|9674.312|25.21951|13|  

> [!TIP]
> Each time you run [Compute Elementary Statistics](compute-elementary-statistics.md), it can generate only a single summary statistic for each of the selected columns. However, you can use the [Add Columns](add-columns.md) or [Add Rows](add-rows.md) modules to merge the results into a single table, as in the preceding example.
  
##  <a name="bkmk_SupportedStats"></a> Supported statistics  

This module supports the following standard descriptive statistics.  
  
### Deviation squared  

Calculates the *squared deviation* of the column values. Also known as the sum of squares.    

Squared deviation is a measure of how far values are dispersed from the mean.  
  

### Geometric mean  

Calculates the *geometric mean* of the column values.  
  
The geometric mean can be used to measure the central tendency of a set of numbers. Compared to the arithmetic mean, it is less affected by a small number of extreme values. It can also be used to compare measurements on different scales, since it effectively normalizes the scales of the numbers being compared. The geometric means is sometimes used to estimate compound annual growth rates.  
  
The equivalent function in Excel is GEOMEAN.  
  
### Harmonic mean  

Calculates the *harmonic mean* of the column values.  
  
To compute the harmonic mean, all values are converted to their reciprocals, and then the mean is taken of those values. The harmonic mean is the reciprocal of that mean. If the column values are positive, larger numbers are weighted less than smaller numbers.  
  
The harmonic mean is always less than the geometric mean, which is always less than the arithmetic mean. The harmonic mean is useful for averaging variables that represent rates, such as speed (distance over time) or sales per quarter.  
  
The equivalent function in Excel is HARMEAN.  
  
### Interquartile distance  

Calculates the *interquartile difference* for the first and the last *quartiles* of the column values. Also called the *quartile range*. When the quartile falls between two numbers, the quartile value is the average of the two values on either side of the cut.  
  
The quartile value divides the column of values into four groups with an equal number of values. Thus, one quarter of the values are less than or equal to the 25th percentile. Three quarters of the values are less than or equal to the 75th percentile. By reviewing the quartile range you can get an idea of how widely spread the data values are.  
  
### K-th central moment  

Calculates *K-th central moment* for the column values.  

When calculating K-th central moment, you must also specify the **Order**, meaning the value of k.  The value of k can range from 0 to any allowed integer value, though higher order values are generally not meaningful.

Generally, in descriptive statistics, a moment is a measure that describes the shape of a set of points. Central moments are moments about the mean, which are usually used because they provide better information about the distribution's shape.   An order of 2 usually represents the variance; an order of 4 is used for kurtosis. The first order moment is the mean. Thus the collection of all moments uniquely describes the distribution of values in the column.

### Max

Finds the *maximum value* in the column.

### Mean

Calculates the *arithmetic mean* of the column values.

The equivalent function in Excel is AVERAGE.

### Mean deviation

Calculates the *mean absolute deviation* for the column values.

That is, the mean is computed for the column, and the deviation computed for each value in the column.  The average of the absolute values of the individual deviation values is the mean deviation.

This statistic tells you how spread out from the mean your column of numbers is.

### Median

Returns the *median* of the column values.

The median is the number in the middle of a column of numbers.  If there is an even number of numbers in the column, the median is the average of the two numbers in the middle.

The median, together with the *mean* and the *mode*, is one of three statistics that measures central tendency. If the values are symmetrical around the mean, the three numbers will be about the same. However, the median is more robust to outliers than the mean.

### Median deviation

Calculates the *median deviation* for the column.

That is, the median is computed for the column, and the deviation computed for each value in the column.  The median value of the absolute values of the individual deviation values is taken.

The median absolute deviation is also known as MAD, and is used to describe the variability of a sample of numbers. MAD tells you how spread out from the mean your column of numbers is.

### Min

Returns the *minimum value* of the column values.

### Mode

Finds all *modes* for the column.

The mode is the value that appears the most in the column. If several values appear the same number of times, the column can have multiple modes.

As a measure of central tendency, mode is more robust to outliers than the mean, and can be used with nominal data too.

### Population standard deviation

Calculates the *population standard deviation* for the column values.

This statistic assumes that the column values represent the entire population. If your data is only a sample of the population, you must compute the standard deviation by using **Sample standard deviation**. However, in large datasets, the two statistics return approximately equal values.

The standard deviation is computed as the square root of the column variance. This statistic captures the amount of variability in the column.

### Population variance

Calculates the *population variance* for the column values.

Variance measures how much a set of numbers is spread out. If variance is zero, all numbers are the same.  

This statistic assumes that the column of values represents the entire population. If your data contains only a sample of the values, you should compute variance by using **Sample variance**.

The equivalent Excel function is `VAR.P`.  


### Product

Calculates the *product* of the column's elements.  
  
To get the product, you multiple all the numbers in the column. The result is not in itself useful as a descriptive statistic but the function is useful for a variety of other calculations.  
  
### Range

Calculates the *range* of the column values. The range is defined as the maximum value minus the minimum value

### Sample kurtosis

Calculates the *sample kurtosis* for the column values.  
  
Kurtosis describes the shape of the distribution of values-- that is, how peaked or flat the distribution of values is, compared with the normal distribution.  

-   The normal distribution has a kurtosis of 0.  
  
-   High kurtosis values indicate that the probability mass is concentrated either around a peak, or in the tail of the distribution.  
  
-   Negative kurtosis values indicate a relatively flat distribution.  

### Sample skewness

Calculates the *sample skewness* for the column values.  

Skew describes whether the bulk of the values are at the center, shifted to the left, or shifted to the right. Two distributions might have the same mean and standard deviation, yet be shaped very differently. You can use skewness and kurtosis to characterize the shape.  
  
-   Negative skew values means the distribution is skewed to the left.  
  
-   0 denotes the normal distribution.  
  
-   Positive skewness values mean the distribution is skewed to the right.  

### Sample standard deviation

Calculates the *sample standard deviation* for the column values.  
  
The standard deviation of the sample measures how spread out the values in the column are from the mean. It represents the average distance between the values of the data in the set and the mean.  
  
This statistic assumes that the column values represent a sample of the population. If your data represents the entire population, you must compute the standard deviation using **Population standard deviation**.  
  
The equivalent Excel function is ST.DEV.S.  
  
### Sample variance

Calculates the *sample variance* for the column values.  
  
This method assumes that the column values represent a sample of the population. If the column contains the entire population, you should use **Population standard variance**.  
  
The equivalent Excel function is VAR.S.  

### Sum

Calculates the *sum* of the column values.  

## Examples  

The following experiments in the [Azure AI Gallery](https://gallery.azure.ai/) demonstrate how you can create a summary report that contains descriptive statistics for an entire dataset. The summary report contains only general statistics; however, you can save it as a dataset and then add more detailed statistics, using the options in [Compute Elementary Statistics](compute-elementary-statistics.md).

- [Download dataset from UCI](https://gallery.azure.ai/Experiment/24c4e869c5c448958ce923c2e2bfbb27): The [Summarize Data](summarize-data.md) module is used to generate a summary report on all columns in the dataset.  
  
- [Dataset Processing and Analysis](https://gallery.azure.ai/Experiment/943c3d4becb7470e8acac6af699d6ea9): The [Summarize Data](summarize-data.md) module is used to generate a summary report on all columns in the dataset.  


##  Technical notes  

This section contains implementation details, tips, and answers to frequently asked questions.

> [!TIP]
> The following conditions must be satisfied when using the [Compute Elementary Statistics](compute-elementary-statistics.md) module:  
> 
> - There must be a sufficient number of data points (rows) to compute the selected statistic. For example, to compute **Sample standard deviation** requires at least two data points; otherwise, the result is NaN.  
> - Input columns must be numeric or Boolean.  
> 
> By default, all numeric columns are selected. However, if any numeric columns are marked as categorical, you might get the following error: " Error 0056: Column with name \<column name> is not in an allowed category."
> To correct the error, add an instance of the [Edit Metadata](edit-metadata.md) module, select the column with the problem, and use the option **Remove categorical**.  

### Implementation details
  
Boolean columns are processed as follows:  
  
+ MIN is computed as logical AND.  
  
+ MAX is computed as logical OR.  
  
+ RANGE checks whether the number of unique values in the column equals 2.  
  
+ Missing values are ignored.  
  
+ For statistics that require floating-point calculations, True = 1.0 and False = 0.0

## Expected inputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Input dataset|  
  
## Module parameters

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Method|List|Elementary statistics method||Selects a statistical method to use in calculations. See How to use section for list of values.|  
|Column set|any|ColumnSelection|NumericAll|Selects the columns for which to calculate the statistic|  
|Order|>=1|Integer|3|Specifies a value for central moment order (used for the kth central moment only)|  
  
## Output  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Results dataset|[Data Table](data-table.md)|Output dataset|  

## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0017](errors/error-0017.md)|Exception occurs if one or more specified columns have a type that is unsupported by the current module.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).  

## See also

 [Statistical Functions](statistical-functions.md)   
 [elementary](compute-elementary-statistics.md)   
 [Summarize Data](summarize-data.md)   
 [A-Z Module List](a-z-module-list.md)
