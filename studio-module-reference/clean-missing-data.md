---
title: "ML Studio (classic): Clean Missing Data - Azure"
description: Learn how to use the Clean Missing Data module to remove, replace, or infer missing values.
ms.date: 05/06/2019
ms.service: "machine-learning"
ms.subservice: "studio-classic"
ms.topic: "reference"

author: xiaoharper
ms.author: amlstudiodocs

---
# Clean Missing Data

*Specifies how to handle the values missing from a dataset*  

Category: [Data Transformation / Manipulation](data-transformation-manipulation.md)  

[!INCLUDE [studio-ui-applies-label](../includes/studio-ui-applies-label.md)]
  
## Module overview  

This article describes how to use the [Clean Missing Data](clean-missing-data.md) module in Azure Machine Learning Studio (classic), to remove, replace, or infer missing values. 

Data scientists often check data for missing values and then perform various operations to fix the data or insert new values. The goal of such cleaning operations is to prevent problems caused by missing data that can arise when training a model. 

This module supports multiple type of operations for "cleaning" missing values, including:

+ Replacing missing values with a placeholder, mean, or other value
+ Completely removing rows and columns that have missing values
+ Inferring values based on statistical methods

> [!TIP]
> New to machine learning? This article provides a good explanation of why you would use each of the different methods for replacing missing values: [Methods for handling missing values](https://gallery.azure.ai/Experiment/Methods-for-handling-missing-values-1)  

Using this module does not change your source dataset. Instead, it creates a new dataset in your workspace that you can use in the subsequent workflow. You can also save the new, cleaned dataset for reuse.

This module also outputs a definition of the transformation used to clean the missing values. You can re-use this transformation on other datasets that have the same schema, by using the [Apply Transformation](apply-transformation.md) module.  

## How to use Clean Missing Data

This module lets you define a cleaning operation. You can also save the cleaning operation so that you can apply it later to new data. See the following links for a description of how to create and save a cleaning process: 
 
+ [To replace missing values](#bkmk_ReplaceMissing)  
  
+ [To apply a cleaning transformation to new data](#bkmk_Apply)  
 
> [!IMPORTANT]
> The cleaning method that you use for handling missing values can dramatically affect your results. We recommend that you experiment with different methods. Consider both the justification for use of a particular method, and the quality of the results.

###  <a name="bkmk_ReplaceMissing"></a> Replace missing values  

Each time that you apply the  [Clean Missing Data](clean-missing-data.md) module to a set of data, the same cleaning operation is applied to all columns that you select. Therefore, if you need to clean different columns using different methods, use separate instances of the module.

1.  Add the [Clean Missing Data](clean-missing-data.md) module to your experiment, and connect the dataset that has missing values.  
  
2.  For **Columns to be cleaned**, choose the columns that contain the missing values you want to change. You can choose multiple columns, but you must use the same replacement method in all selected columns. Therefore, typically you need to clean string columns and numeric columns separately.

    For example, to check for missing values in all numeric columns:

    1. Open the Column Selector, and select **WITH RULES**.
    2. For **BEGIN WITH**, select **NO COLUMNS**.

        You can also start with ALL COLUMNS and then exclude columns. Initially, rules are not shown if you first click **ALL COLUMNS**, but you can click **NO COLUMNS** and then click **ALL COLUMNS** again to start with all columns and then filter out (exclude) columns based on the name, data type, or columns index.

    3. For **Include**, select **Column type** from the dropdown list, and then select **Numeric**, or a more specific numeric type. 
  
    Any cleaning or replacement method that you choose must be applicable to **all** columns in the selection. If the data in any column is incompatible with the specified operation, the module returns an error and stops the experiment.
  
3.  For **Minimum missing value ratio**, specify the minimum number of missing values required for the operation to be performed.  
  
    You use this option in combination with **Maximum missing value ratio** to define the conditions under which a cleaning operation is performed on the dataset. If there are too many or too few rows that are missing values, the operation cannot be performed. 
  
    The number you enter represents the **ratio** of missing values to all values in the column. By default, the **Minimum missing value ratio** property is set to 0. This means that missing values are cleaned even if there is only one missing value. For an example of how to use this option, see [Setting a Threshold for Cleaning Operations](#bkmk_SettingThreshold). 

    > [!WARNING]
    > This condition must be met by each and every column in order for the specified operation to apply. For example, assume you selected three columns and then set the minimum ratio of missing values to .2 (20%), but only one column actually has 20% missing values. In this case, the cleanup operation would apply only to the column with over 20% missing values. Therefore, the other columns would be unchanged.
    > 
    > If you have any doubt about whether missing values were changed, select the option, **Generate missing value indicator column**. A column is appended to the dataset to indicate whether or not each column met the specified criteria for the minimum and maximum ranges.  
  
4. For **Maximum missing value ratio**, specify the maximum number of missing values that can be present for the operation to be performed.   
  
    For example, you might want to perform missing value substitution only if 30% or fewer of the rows contain missing values, but leave the values as-is if more than 30% of rows have missing values.  
  
    You define the number as the ratio of missing values to all values in the column. By default, the **Maximum missing value ratio** is set to 1. This means that missing values are cleaned even if 100% of the values in the column are missing.  
  
    > [!NOTE]
    > When you set a threshold using the options  **Minimum missing value ratio** or **Maximum missing value ratio**, the cleaning operation cannot be performed if even one of the selected columns does not meet the criteria.
  
5. For **Cleaning Mode**, select one of the following options for replacing or removing missing values:  
  
    + **Replace using MICE**: For each missing value, this option assigns a new value, which is calculated by using a method described in the statistical literature as "Multivariate Imputation using Chained Equations" or "Multiple Imputation by Chained Equations".  With a  *multiple imputation method*, each variable with missing data is modeled conditionally using the other variables in the data before filling in the missing values. In contrast, in a *single imputation method* (such as replacing a missing value with a column mean) a single pass is made over the data to determine the fill value.
  
        All imputation methods introduce some error or bias, but multiple imputation better simulates the process generating the data and the probability distribution of the data.  
  
        For a general introduction to methods for handling missing values, see [Missing Data: the state of the art. Schafer and Graham, 2002](https://www.academia.edu/1045565/Missing_Data_Our_View_of_the_State_of_the_Art).  
  
        > [!WARNING]
        > This option cannot be applied to completely empty columns. Such columns must be removed or passed to the output as is.  
  
    + **Custom substitution value**: Use this option to specify a placeholder value (such as a 0 or NA) that applies to all missing values. The value that you specify as a replacement must be compatible with the data type of the column.
  
    + **Replace with mean**: Calculates the column mean and uses the mean as the replacement value for each  missing value in the column.  
  
        Applies only to columns that have Integer, Double, or Boolean data types. See the [Technical Notes](#bkmk_TechNotes) section for more information.  
  
    + **Replace with median**: Calculates the column median value, and uses the median value as the replacement for any missing value in the column.  
  
        Applies only to columns that have Integer or Double data types. See the [Technical notes](#bkmk_TechNotes) section for more information.  
  
    + **Replace with mode**: Calculates the mode for the column, and uses the mode as the replacement value for every missing value in the column.  
  
        Applies to columns that have Integer, Double, Boolean, or Categorical data types. See the [Technical Notes](#bkmk_TechNotes) section for more information.  
  
    + **Remove entire row**: Completely removes any row in the dataset that has one or more missing values. This is useful if the missing value can be considered randomly missing.  
  
    + **Remove entire column**: Completely removes any column in the dataset that has one or more missing values.  
  
    + **Replace using Probabilistic PCA**: Replaces the missing values by using a linear model that analyzes the correlations between the columns and estimates a low-dimensional approximation of the data, from which the full data is reconstructed. The underlying dimensionality reduction is a probabilistic form of Principal Component Analysis (PCA), and it implements a variant of the model proposed in the Journal of the Royal Statistical Society, Series B 21(3), 611–622 by Tipping and Bishop.  
  
        Compared to other options, such as Multiple Imputation using Chained Equations (MICE), this option has the advantage of not requiring the application of predictors for each column. Instead, it approximates the covariance for the full dataset. Therefore, it might offer better performance for datasets that have missing values in many columns.
  
         The key limitations of this method are that it expands categorical columns into numerical indicators and computes a dense covariance matrix of the resulting data. It also is not optimized for sparse representations. For these reasons, datasets with large numbers of columns and/or large categorical domains (tens of thousands) are not supported due to prohibitive space consumption.  
  
        > [!TIP]
        > Remember that the method you choose is applied to all columns in the selection. Thus, if you want to replace some missing values with zeroes in some columns but insert a placeholder in other columns, you should use [Select Columns in Dataset](select-columns-in-dataset.md) to separate the data and use different instances of the [Clean Missing Data](clean-missing-data.md) module.  
  
6. The option **Replacement value** is available if you have selected the option, **Custom substitution value**. Type a new value to use as the replacement value for all missing values in the column.  
  
    Note that you can use this option only in columns that have the Integer, Double, Boolean, or Date data types. For date columns, the replacement value can also be entered as the number of 100-nanosecond ticks since 1/1/0001 12:00 A.M.  
  
7. **Generate missing value indicator column**: Select this option if you want to output some indication of whether the values in the column met the criteria for missing value cleaning. This option is particularly useful when you are setting up a new cleaning operation and want to make sure it works as designed.
  
8. Run the experiment, or select the [Clean Missing Data](clean-missing-data.md) module and click **Run selected**.  

### Results

The module returns two outputs:  

-   **Cleaned dataset**: A dataset comprised of the selected columns, with missing values handled as specified, along with an indicator column, if you selected that option.  

    Columns not selected for cleaning are also "passed through".  
  
-  **Cleaning transformation**: A data transformation used for cleaning, that can be saved in your workspace and applied to new data later.

###  <a name="bkmk_Apply"></a> Apply a saved cleaning operation to new data  

If you need to repeat cleaning operations often, we recommend that you save your recipe for data cleansing as a *transform*, to reuse with the same dataset. Saving a cleaning transformation is particularly useful if you must frequently re-import and then clean data that has the same schema.  
      
1.  Add the [Apply Transformation](apply-transformation.md) module to your experiment.  
  
2.  Add the dataset you want to clean, and connect the dataset to the right-hand input port.  
  
3.  Expand the **Transforms** group in the left-hand pane of Studio (classic). Locate the saved transformation and drag it into the experiment.  
  
4.  Connect the saved transformation to the left input port of [Apply Transformation](apply-transformation.md). 

    When you apply a saved transformation, you cannot select the columns to which the transformation are applied. That is because the transformation has been already defined and applies automatically to the data types specified in the original operation.

    However, suppose you created a transformation on a subset of numeric columns. You can apply this transformation to a dataset of mixed column types without raising an error, because the missing values are changed only in the matching numeric columns.

6.  Run the experiment.  

## Examples

See examples of how this module is used in the [Azure AI Gallery](https://gallery.azure.ai/):  
  
-   [Prediction of student performance](https://go.microsoft.com/fwlink/?LinkId=525727): In this sample, zeros are inserted for missing values.  
  
-   [Cross Validation for Binary Classifier sample](https://go.microsoft.com/fwlink/?LinkId=525734): Zeros are used to fill-in for missing values, and an indicator column is created to track the changes. Columns with all missing values are also retained.  
  
-   [Dataset Processing and Analysis](https://go.microsoft.com/fwlink/?LinkId=525733): In this sample, different branches of the experiment use different methods for missing value substitution, and the datasets are then evaluated by using [Summarize Data](summarize-data.md) and [Compute Linear Correlation](compute-linear-correlation.md).
  
-   [Flight delay prediction sample](https://go.microsoft.com/fwlink/?LinkId=525725): Empty rows are removed entirely.  
  
##  <a name="bkmk_TechNotes"></a> Technical notes  

This section contains implementation details, as well as known issues and commonly asked questions.
  
-   An error occurs if the mean or median option is used when any string columns are selected. If you need to process columns of different data types, create two instances of **Clean Missing Data**.  
  
-   When replacing missing values with a mean value in columns with the Boolean, Integer, DateTime, or TimeSpan data types, the column is first converted to floating point numbers, the mean is calculated, and then the result is rounded to the nearest value of the original data type.  
  
-   When you type a replacement value, the value must be compatible with the data type in the selected column.  
  
-   Values of `NaN`, `Inf`, and `–Inf` are allowed for columns where the data type is Double.
  
-   When using the MICE method, the replacement value is predicted by using the trained MICE model.  
  
-   Using **Clean Missing Data** can reset other column types to **feature**. If your data contains other types of columns, such as labels, use [Edit Metadata](edit-metadata.md) to correct the column types.
  
### Restrictions on use of cleaning transformations

The following restrictions apply when you use a saved transformation  (based on **Clean Missing Data**) to new data:  
  
-   A saved transformation cannot generate indicator values, even if this option was used in the original cleaning operation. Consider the indicator values as most useful when testing a new transformation.  
  
-   The transformation does not calculate new values based on the new dataset. In other words, if you used [Clean Missing Data](clean-missing-data.md) on Dataset A and generated a mean value of 0.5, that same value would be applied as the mean for replacing missing values in Dataset B, regardless of the actual values in Dataset B.  
  
-   The data type of the columns in the new dataset must match the data type of the columns on which the transformation was originally created. An error is raised if any operations are performed on the column that implicitly change the data type.
  
    For example, suppose you create a mean for an integer data column [Col1], and save the transformation. Now you want to apply the cleanup transformation to a copy of [Col1] that has been adjusted using a formula, such as ([Col1] /1.5). To ensure that the result is an integer, you round up the result, but still get an error when you apply the transformation. However, if you adjust the value using a formula such as ([Col 1] * 10), no error is raised!
    
    To avoid such issues, use [Edit Metadata](edit-metadata.md) to explicitly reset the data type to integer. In general, operations in [Apply Math Operation](apply-math-operation.md) module implicitly change numeric columns to `double`.
  
###  <a name="bkmk_SettingThreshold"></a> Setting and interpreting threshold values

When you specify a threshold for cleaning operations using the options **Minimum missing value ratio** or **Maximum missing value ratio**, the results can be unexpected or confusing. To illustrate how the options for maximum and minimum missing values work, we have provided some examples from the **Automobile Prices** sample dataset, which has many columns with missing values. 

The following table shows the count of missing values for several columns in that dataset, together with the ratio of missing values computed on the dataset. The ratio of missing values (in the rightmost column) is the value that would be used in evaluating the dataset against the specified threshold values.
  
Assume that you set **Minimum missing value ratio** to 0.019 and set  **Maximum missing value ratio** to 0.020. Given the following table of values, some columns meet the threshold criteria, and some do not:

-   The columns `bore` and `stroke` meet the threshold criteria.
-   The columns `normalized-losses` and `compression-ratio` do not meet the threshold criteria.

|Column name|Count of missing values|Ratio of missing values|  
|-----------------|-----------------------------|-----------------------------|  
|Normalized-losses|41|0.2|  
|Bore|4|0.019512195|  
|Stroke|4|0.019512195|  
|Compression ratio|0|0|  

Because **some** columns in the selection did not meet the specified criteria, no cleaning operation was performed on any column. To help you figure out what happened, the module returns the value **FALSE** in the two indicator columns, `bore_IsMissing` and `stroke_IsMissing`.
  
However, if you change the threshold back to the default values of 0 for **Minimum missing value ratio** and 1 for **Maximum missing value ratio**, an indicator column is returned for all selected columns, and the specified operation is performed.
  
> [!TIP]
>  If you are uncertain about whether missing value clean-up is working as expected, select the **Generate missing value indicator column** option.  

### Known issues

If you use the MICE method to clean data and then process a dataset that contains missing values, you might get the following error:  "AFx Library library exception: Model is not trained. ( Error 1000 )"

This error occurs only when the MICE method is selected, and if the training dataset does not contain missing values but the test dataset does.

## Expected inputs  

|Name|Type|Description|  
|----------|----------|-----------------|  
|Dataset|[Data Table](data-table.md)|Dataset to be cleaned|  

## Module parameters  

|Name|Range|Type|Default|Description|  
|----------|-----------|----------|-------------|-----------------|  
|Columns to be cleaned|Any|ColumnSelection|All|Select columns for the missing values clean operation.|  
|Minimum missing value ratio|[0.0;1.0]|Float|0.0|Clean only column with missing value ratio above the specified value, out of a set of all selected columns.|  
|Maximum missing value ratio|[0.0;1.0]|Float|1.0|Clean only columns with missing value ratio below the specified value out of a set of all selected columns.|  
|Cleaning mode|List|Handling policy|Custom substitution value|Choose an algorithm to use when cleaning missing values.|  
|Replacement value|Any|String|"0"|Type a value to take the place of missing values.<br /><br /> This value is optional.|  
|Cols with all missing values|Any|ColumnsWithAllValuesMissing|Remove|Indicate if columns of all missing values should be preserved in the output.|  
|Generate missing value indicator column|Any|Boolean|false|Generate a column that indicates which rows were cleaned.|  
|Number of iterations|[1;10]|Integer|5|Specify the number of iterations when using MICE.|  
|Number of iterations for PCA prediction|[1;50]|Integer|10|Specify the number of iterations when using a PCA prediction.|  
  
## Outputs

|Name|Type|Description|  
|----------|----------|-----------------|  
|Cleaned dataset|[Data Table](data-table.md)|Cleaned dataset|  
|Cleaning transformation|[ITransform interface](itransform-interface.md)|Transformation that is to be passed to the **Apply Transformation** module to clean new data.|  
  
## Exceptions

|Exception|Description|  
|---------------|-----------------|  
|[Error 0002](errors/error-0002.md)|An exception occurs if one or more parameters could not be parsed or converted from the specified type into the type required by the target method.|  
|[Error 0003](errors/error-0003.md)|An exception occurs if one or more input datasets are null or empty.|  
|[Error 0008](errors/error-0008.md)|An exception occurs if a parameter is not in range.|  
|[Error 0013](errors/error-0013.md)|An exception occurs if the leaner passed to the module has an invalid type.|  
|[Error 0018](errors/error-0018.md)|An exception occurs if the input dataset is not valid.|  
|[Error 0039](errors/error-0039.md)|An exception occurs if the operation fails.|  

For a list of errors specific to Studio (classic) modules, see [Machine Learning Error codes](errors/machine-learning-module-error-codes.md).

For a list of API exceptions, see [Machine Learning REST API Error Codes](/azure/machine-learning/studio/web-service-error-codes).

## See also

 [Manipulation](data-transformation-manipulation.md)   
 [Data Transformation](data-transformation.md)   
 [A-Z Module List](a-z-module-list.md)
